# Animating SceneKit Content
Learn about implicit animations, explicit animations, and actions, and when to choose each in your app.

암시적 애니메이션, 명시적 애니메이션 및 액션에 대해 알아보고 앱에서 각각을 언제 선택할 것인가.

## Overview
SceneKit animation support is based on the Core Animation framework. (For more about Core Animation, read [Core Animation Programming Guide][1].) Several SceneKit classes define animatable properties, meaning that in addition to simply assigning a new value to the property, you can create animations that transition smoothly between two values of the property. For example, animating a node’s opacity property fades the node’s visible content in or out. You can animate content implicitly or explicitly.

SceneKit 애니메이션 지원은 Core Animation 프레임 워크를 기반으로합니다. (Core Animation에 대한 자세한 내용은 [Core Animation Programming Guide][1]를 참조하십시오.) 여러 SceneKit 클래스는 애니메이션 가능한 속성을 정의합니다. 즉, 단순히 속성에 새 값을 할당하는 것 외에도 두 속성 값 사이를 부드럽게 전환하는 애니메이션을 만들 수 있습니다. 예를 들어, 노드의 불투명도 속성에 애니메이션을 적용하면 노드의 표시 내용이 페이드 인 또는 페이드 아웃됩니다. 내용을 암시적 또는 명시적으로 애니메이트 할 수 있습니다.

## Animate Content Changes Implicitly
You create an animation implicitly by changing the value of an animatable property. Implicit animation is useful when you want to quickly animate a one-time change or animate several property changes together without writing a lot of animation code.

The [SCNTransaction][2] class defines SceneKit's architecture for scene content changes, including implicit animations: A transaction is a single atomic operation that combines multiple changes to nodes, geometries, materials, or other scene content. By default, SceneKit automatically creates a default transaction for all changes you make to a scene during one pass through the run loop.

The default transaction’s duration is zero, so the changes you make to animatable properties occur immediately. However, if you increase the transaction’s animationDuration, all changes to animatable properties automatically animate. For example, changing the animation duration in an IBAction method causes both the position and opacity changes in that method to animate together.

```Swift
@IBAction func fallAndFade(_ sender: Any) {
    SCNTransaction.animationDuration = 1.0
    textNode.position.y = -10
    textNode.opacity = 0
}
```

animatable 속성의 값을 변경하여 암시적으로 애니메이션을 만듭니다. 암시적 애니메이션은 일회성 변화를 신속하게 애니메이션으로 만들거나 많은 애니메이션 코드를 작성하지 않고 여러 속성 변경 사항을 함께 애니메이션하려는 경우에 유용합니다.

[SCNTransaction][2] 클래스는 암시적 애니메이션을 포함하여 scene 컨텐츠 변경을 위한 SceneKit의 아키텍처를 정의합니다. 트랜잭션은 노드, 지오메트리, 재질 또는 기타 장면 컨텐츠에 대한 여러 변경 사항을 결합하는 단일 최소 작업입니다. 기본적으로 SceneKit은 런 루프를 한 번 통과하는 동안 장면에 대한 모든 변경 사항에 대한 기본 트랜잭션을 자동으로 생성합니다.

기본 트랜잭션의 지속 시간은 0이므로 애니메이션 가능한 속성에 대한 변경 사항은 즉시 발생합니다. 그러나 트랜잭션의 animationDuration을 늘리면 애니메이션 가능한 속성에 대한 모든 변경 사항이 자동으로 애니메이션으로 나타납니다. 예를 들어 IBAction 메서드에서 애니메이션 지속 시간을 변경하면 해당 메서드의 위치와 불투명도가 동시에 변경됩니다.

```Swift
@IBAction func fallAndFade(_ sender: Any) {
    SCNTransaction.animationDuration = 1.0
    textNode.position.y = -10
    textNode.opacity = 0
}
```

## Explicitly Create an Animation
For more complex animations, you can explicitly create an animation object and attach it to the scene element being animated. Creating an animation object also makes an animation reusable, so you can play the same animation at any time on demand or apply it to different elements of your scene.

Choose a [CAAnimation][3] subclass for the type of animation you want to create, specify the property to be animated using key-value coding, and set animation parameters. You then set the animation in motion by attaching it to one or more elements of your scene, as shown in Listing 2.

By using different Core Animation classes, you can combine or sequence several animations or create animations that interpolate a property’s value between several keyframe values. For more about creating animation objects, see [Core Animation Programming Guide][1]. For more about attaching animations to SceneKit objects, see [SCNAnimatable][4].

Listing 2. Explicit animation to vary the 3D extrusion depth of a block of text
```Swift
let animation = CABasicAnimation(keyPath: "geometry.extrusionDepth")
animation.fromValue = 0.0
animation.toValue = 100.0
animation.duration = 1.0
animation.autoreverses = true
animation.repeatCount = .infinity
textNode.addAnimation(animation, forKey: "extrude")
```

SceneKit also uses CAAnimation objects for animations created using external 3D authoring tools and saved in scene files. For example, an artist might create a game character with animations for walking, jumping, and other actions. You incorporate these animations into your game by loading animation objects from the scene file using the [SCNSceneSource][5] class and attaching them to the SCNNode object that represents the game character.


보다 복잡한 애니메이션의 경우, 명시적으로 애니메이션 오브젝트를 생성하여 애니메이션이 적용되는 장면 요소에 첨부 할 수 있습니다. 애니메이션 오브젝트를 생성하면 애니메이션을 재사용 할 수 있으므로 필요에 따라 언제든지 같은 애니메이션을 재생하거나 장면의 다른 요소에 적용 할 수 있습니다.

생성하려는 애니메이션 유형에 대한 [CAAnimation][3] 서브 클래스를 선택하고, 키 - 값 코딩을 사용하여 애니메이트 할 속성을 지정하고, 애니메이션 매개 변수를 설정하십시오. 그런 다음 장면의 하나 이상의 요소에 애니메이션을 첨부하여 애니메이션을 설정합니다 (목록 2 참조).

다른 Core Animation 클래스를 사용하면 여러 애니메이션을 결합하거나 시퀀스 할 수 있으며 여러 키 프레임 값 사이에서 속성 값을 보간하는 애니메이션을 만들 수 있습니다. 애니메이션 객체 생성에 대한 자세한 내용은 [Core Animation Programming Guide][1]를 참조하십시오. SceneKit 객체에 애니메이션을 첨부하는 방법에 대한 자세한 내용은 [SCNAnimatable][4]을 참조하십시오.

목록 2. 텍스트 블록의 3D 돌출 깊이를 변경하는 명시적 애니메이션
```Swift
let animation = CABasicAnimation(keyPath: "geometry.extrusionDepth")
animation.fromValue = 0.0
animation.toValue = 100.0
animation.duration = 1.0
animation.autoreverses = true
animation.repeatCount = .infinity
textNode.addAnimation(animation, forKey: "extrude")
```

또한 SceneKit은 외부 3D 저작 도구를 사용하여 생성되고 scene 파일에 저장된 애니메이션에 CAAnimation 객체를 사용합니다. 예를 들어, 아티스트는 걷기, 점프 및 기타 동작을 위한 애니메이션이 있는 게임 캐릭터를 만들 수 있습니다. [SCNSceneSource][5] 클래스를 사용하여 scene 파일에서 애니메이션 개체를 로드하고 게임 캐릭터를 나타내는 SCNNode 객체에 연결하여 이러한 애니메이션을 게임에 통합합니다.

[Apple Documents][apple]


[1]: https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/CoreAnimation_guide/Introduction/Introduction.html#//apple_ref/doc/uid/TP40004514
[2]: /01_iOS/SceneKit/Animation/SCNTransaction.md
[3]: /01_iOS/Core_Animation/CAAnimation.md
[4]: /01_iOS/SceneKit/Animation/SCNAnimatable.md
[5]: /01_iOS/SceneKit/SCNSceneSource.md
[apple]: https://developer.apple.com/documentation/scenekit/animation/animating_scenekit_content
