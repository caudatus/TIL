# SCNAnimatable - Protocol
The common interface for attaching animations to nodes, geometries, materials, and other SceneKit objects.

애니메이션을 노드, 지오메트리, 머티리얼 및 기타 SceneKit 객체에 첨부하기 위한 공통 인터페이스입니다.

## Overview
SceneKit uses the same architecture as the Core Animation framework, allowing you to animate property changes implicitly or explicitly. For implicit animation, use the [SCNTransaction][1] class to quickly create simple animations with very little code. For more complex animations, explicitly create [CAAnimation][2] objects, and use the methods in the SCNAnimatable protocol to attach them to the SceneKit objects you want to animate. You also use the methods in this protocol to control any animations already attached to a SceneKit object.

For example, making a node spin continuously for as long as it appears in the scene graph requires explicitly creating an animation that repeats. The following code creates such an animation and attaches it to a node:

```Swift
CABasicAnimation *rotationAnimation = [CABasicAnimation animationWithKeyPath:@"rotation"];
// Animate one complete revolution around the node's Y axis.
rotationAnimation.toValue = [NSValue valueWithSCNVector4:SCNVector4Make(0, 1, 0, M_PI * 2)];
rotationAnimation.duration = 10.0; // One revolution in ten seconds.
rotationAnimation.repeatCount = FLT_MAX; // Repeat the animation forever.
[node addAnimation:rotationAnimation forKey:nil]; // Attach the animation to the node to start it.
```

SceneKit은 Core Animation 프레임 워크와 동일한 아키텍처를 사용하여 암시적 또는 명시적으로 속성 변경 사항에 애니메이션을 적용 할 수 있습니다. 암시적 애니메이션의 경우 [SCNTransaction][1] 클래스를 사용하여 간단한 코드로 간단한 애니메이션을 빠르게 만들 수 있습니다. 보다 복잡한 애니메이션의 경우 [CAAnimation][2] 객체를 명시적으로 생성하고 SCNAnimatable 프로토콜의 메소드를 사용하여 애니메이션하려는 SceneKit 객체에 추가하십시오. 또한 이 프로토콜의 메소드를 사용하여 이미 SceneKit 객체에 연결된 애니메이션을 제어합니다.

예를 들어 scene 그래프에 나타나는 한 노드를 계속 회전 시키려면 반복되는 애니메이션을 명시 적으로 작성해야합니다. 다음 코드는 이러한 애니메이션을 만들어 노드에 연결합니다.

```Swift
CABasicAnimation *rotationAnimation = [CABasicAnimation animationWithKeyPath:@"rotation"];
// Animate one complete revolution around the node's Y axis.
rotationAnimation.toValue = [NSValue valueWithSCNVector4:SCNVector4Make(0, 1, 0, M_PI * 2)];
rotationAnimation.duration = 10.0; // One revolution in ten seconds.
rotationAnimation.repeatCount = FLT_MAX; // Repeat the animation forever.
[node addAnimation:rotationAnimation forKey:nil]; // Attach the animation to the node to start it.
```

[Apple Documents][apple]

[1]: /01_iOS/SceneKit/Animation/SCNTransaction.md
[2]: /01_iOS/Core_Animation/CAAnimation.md
[apple]: https://developer.apple.com/documentation/scenekit/scnanimatable
