# CAAnimation
The abstract superclass for animations in Core Animation.

Core Animation의 애니메이션을 위한 추상 수퍼 클래스입니다.


## Overview
CAAnimation provides the basic support for the [CAMediaTiming][1] and [CAAction][2] protocols. You do not create instance of CAAnimation: to animate Core Animation layers or SceneKit objects, create instances of the concrete subclasses [CABasicAnimation][3], [CAKeyframeAnimation][4], [CAAnimationGroup][5], or [CATransition][6].

CAAnimation은 [CAMediaTiming][1] 및 [CAAction][2] 프로토콜에 대한 기본 지원을 제공합니다. CAAnimation의 인스턴스를 생성하지 않습니다 : Core Animation 레이어 또는 SceneKit 객체를 애니메이션 하기 위해서는 [CABasicAnimation][3], [CAKeyframeAnimation][4], [CAAnimationGroup][5] 또는 [CATransition][6]의 구체적인 하위 클래스 인스턴스를 생성합니다.


## Animating Core Animation Layers
You can animate the contents of your iOS or macOS app’s user interface by attaching animations to [CALayer][8] objects. For more information, see [Core Animation Programming Guide][7].

[CALayer][8] 객체에 애니메이션을 첨부하여 iOS 또는 macOS 앱의 사용자 인터페이스 내용을 애니메이션으로 만들 수 있습니다. 자세한 내용은 [Core Animation Programming Guide][7]를 참조하십시오.

## Animating Scene Kit Content
In Scene Kit, animation objects represent not only property-based animations, but also animations of geometry data created with external 3D authoring tools and loaded from a scene file. You use the properties of the CAAnimation object representing a geometry animation to control its timing, monitor its progress, and attach actions for Scene Kit to trigger during the animation. You can attach animations to Scene Kit objects that adopt the [SCNAnimatable][9] protocol, including nodes, geometries, and materials.

In a Scene Kit app, CAAnimation objects support additional methods and properties, listed under [Controlling SceneKit Animation Timing][10], [Fading between SceneKit Animations][11], and [Attaching SceneKit Animation Events][12].

Scene Kit에서 애니메이션 객체는 속성 기반 애니메이션뿐만 아니라 외부 3D 저작 도구로 작성되고 scene 파일에서 로드 된 형상 데이터의 애니메이션로도 나타냅니다. 기하 도형 애니메이션을 나타내는 CAAnimation 객체의 속성을 사용하여 타이밍을 제어하고 진행 상황을 모니터링하고 애니메이션 중에 장면 킷에 대한 동작을 트리거 할 수 있습니다. 노드, geometries, materials 를 포함하여 [SCNAnimatable][9] 프로토콜을 채택하는 Scene Kit 오브젝트에 애니메이션을 첨부 할 수 있습니다.

Scene Kit 응용 프로그램에서 CAAnimation 객체는 [Controlling SceneKit Animation Timing][10], [Fading between SceneKit Animations SceneKit Animation][11], [Attaching SceneKit Animation Events][12] 의 추가 메서드 및 속성을 지원합니다.


[Apple Documents][apple]


[1]: https://developer.apple.com/documentation/quartzcore/camediatiming
[2]: https://developer.apple.com/documentation/quartzcore/caaction
[3]: /01_iOS/Core_Animation/CABasicAnimation.md
[4]: /01_iOS/Core_Animation/CAKeyframeAnimation.md
[5]: /01_iOS/Core_Animation/CAAnimationGroup.md
[6]: /01_iOS/Core_Animation/CATransition.md
[7]: https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/CoreAnimation_guide/Introduction/Introduction.html#//apple_ref/doc/uid/TP40004514
[8]: https://developer.apple.com/documentation/quartzcore/calayer
[9]: /01_iOS/SceneKit/Animation/SCNAnimatable.md
[10]: https://developer.apple.com/documentation/quartzcore/caanimation#1668736
[11]: https://developer.apple.com/documentation/quartzcore/caanimation#1668764
[12]: https://developer.apple.com/documentation/quartzcore/caanimation#1668796
[apple]: https://developer.apple.com/documentation/quartzcore/caanimation
