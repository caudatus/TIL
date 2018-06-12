# SCNParticleSystem
An object that animates and renders a system of small image sprites using a high-level simulation whose general behavior you specify.

사용자가 지정하는 일반적인 동작을 가진 high-level 시뮬레이션을 사용하여 작은 이미지 스프라이트로 된 시스템을 애니메이션화하고 렌더링하는 객체입니다.

## Overview
Use [particle systems][1] to create effects such as smoke, rain, confetti, and fireworks.

[입자 시스템][1]을 사용하여 연기, 비, 색종이, 불꽃 놀이와 같은 효과를 만듭니다.

## How Particle Systems Work
Unlike SceneKit nodes and geometries, individual particles are not objects in a scene graph. Because a particle system can involve dozens or hundreds of particles, SceneKit uses a more efficient internal representation that stores and processes the data for all of a system’s particles in bulk.

Instead of accessing each particle to control its behavior or to make it interact with other scene content, you typically use properties of a particle system to control the aggregate behavior of particles. These properties cover several key aspects of the system’s behavior, as summarized below.

- **Appearance.** SceneKit renders a texture image for each particle. Define the appearance of the particle system by specifying an image, its tint color, and rendering parameters such as blending mode. You can even specify an animated image sequence, creating effects like swarms of insects or multi-stage explosions.

- **Life span.** SceneKit creates each particle at a location in the scene (also called an emitter), varies its position and appearance over a specified life span, then removes it from the scene. (Particle creation is also called birth or spawning, and particle removal is also called death.) The total count of particles on screen at any time is the product of the system’s [birthRate][2] and [particleLifeSpan][3] properties. Larger numbers of particles have a greater cost to rendering performance and power usage.

- Emitter behavior. Use the [emitterShape][4] property to specify whether particles spawn from a single point in space or in the region defined by an SCNGeometry object. Use the [emissionDuration][5] property and related properties to vary particle birth over time, so that the system alternates between periods of spawning particles and periods of idle time.

- **Variation.** Particle systems simulate realistic effects by randomly varying particle properties both at birth and over the lifetime of a particle. You can also add random variation to the life span of particles. Several particle system properties have an associated variation property that controls this randomization. For example, the [particleSizeVariation][6] property defines the width of an interval for randomizing the [particleSize][7] property.

- **Movement.** Particles move according to a simple physics simulation—each has an initial direction, speed, angular velocity and acceleration, which SceneKit uses to animate the particle until it dies. You can create many realistic effects using these attributes alone. You can also add more complex behaviors by allowing particles to interact with scene geometry ([colliderNodes][8]), the scene’s [physicsWorld][9] simulation, or [SCNPhysicsField][10] objects.

SceneKit 노드 및 지오메트리와 달리 개별 입자는 scene graph의 객체가 아닙니다. 파티클 시스템은 수십 또는 수백 개의 파티클을 포함 할 수 있기 때문에 SceneKit은 모든 시스템 파티클의 데이터를 대량으로 저장하고 처리하는 보다 효율적인 내부 표현을 사용합니다.

각 입자에 액세스하여 그 동작을 제어하거나 다른 장면 컨텐츠와 상호 작용하는 대신 일반적으로 입자 시스템의 속성을 사용하여 입자의 집합적인 동작을 제어합니다. 이러한 속성은 아래에 요약 된 것처럼 시스템 동작의 몇 가지 주요 측면을 다룹니다.

- **모양.** SceneKit은 각 입자에 대한 텍스처 이미지를 렌더링합니다. 이미지, 색조 색상 및 혼합 모드와 같은 렌더링 매개 변수를 지정하여 입자 시스템의 모양을 정의하십시오. 곤충의 떼 또는 다단계 폭발과 같은 효과를 생성하여 애니메이션 이미지 시퀀스를 지정할 수도 있습니다.
- **수명.** SceneKit은 scene의 한 위치(emitter라고 함)에 각 입자를 만들고 지정된 수명 동안 위치와 모양을 변경 한 다음 scene에서 제거합니다. (입자 생성은 출생 또는 산란이라고도하며 입자 제거는 죽음이라고도합니다.) 언제나 화면에 있는 입자의 총 개수는 시스템의 [birthRate][2] 및 [particleLifeSpan][3] 속성의 결과입니다. 입자 수가 많을수록 렌더링 성능과 전력 사용에 더 많은 비용이 듭니다.
- **Emitter 동작.** [emitterShape][4] 속성을 사용하여 공간의 단일 점 또는 SCNGeometry 객체로 정의 된 영역에서 파티클을 spawn 시킬지 여부를 지정합니다. [emissionDuration][5] 속성과 관련 속성을 사용하여 시간 경과에 따른 입자의 탄생을 다양화 하여 시스템에서 입자가 생성되는 기간과 대기 시간이 번갈아 바뀝니다.
- **변화.** 입자 시스템은 출생시 또는 입자 수명 동안 입자 속성을 무작위로 변경하여 사실적인 효과를 시뮬레이션합니다. 파티클의 수명에 무작위 변형을 추가 할 수도 있습니다. 여러 파티클 시스템 속성에는 이 랜덤화를 제어하는 ​​관련 변형 속성이 있습니다. 예를 들어, [particleSizeVariation][6] 속성은 [particleSize][7] 속성을 임의화할 간격의 너비를 정의합니다.
- **움직임.** 파티클은 단순한 물리 시뮬레이션에 따라 움직입니다. 각 파티클에는 초기 방향, 속도, 각속도 및 가속도가 있으며, SceneKit은 입자가 죽을 때까지 애니메이션을 적용하는 데 사용합니다. 이러한 속성을 단독으로 사용하여 많은 실제 효과를 만들 수 있습니다. 파티클이 scene 지오메트리 ([colliderNodes][8]), 장면의 [physicsWorld][9] 시뮬레이션 또는 [SCNPhysicsField][10] 객체와 상호 작용하도록하여 보다 복잡한 동작을 추가 할 수도 있습니다.

<br/>

In addition, you can also use the following features to add dynamic behaviors to a particle system, changing its appearance over time or making it interact with its environment.

- **Animations and property controllers.** Like many SceneKit objects, the SCNParticleSystem class conforms to the [SCNAnimatable][11] protocol, so you can implicitly or explicitly animate changes to its properties. (For general background on animation, see [Animating SceneKit Content][12].) When you animate changes to a particle system’s properties, these changes affect all particles in the system simultaneously.

To apply animations independently for individual particles, use an [SCNParticlePropertyController][13] object, which associates a [CAAnimation][14] object with a particle system property. With a property controller, you can use features of the Core Animation framework to create time-varying effects that apply to each particle in the system. Typically a Core Animation object varies a property with respect to time, but with a property controller you can also create animations that vary a property based on other input values, such as a particle’s distance from its initial location.

For example, consider a [CAKeyframeAnimation][15] object that animates a series of colors from white to yellow to red, and a particle system that simulates a flame. If you attach this animation to a particle system’s [particleColor][16] property, the resulting flame effect has a single color at any given moment, but that color changes over time. If you instead attach a property controller for the color property, the flame varies in color from its base to its tip—each particle starts out white, then fades to yellow and red as it rises.

- **Spawned particle systems.** When you assign another SCNParticleSystem instance to one of the properties listed in [Spawning Additional Particle Systems][17], SceneKit adds more particle systems to the scene based on the behavior of the original particle system. For example, if you have a particle system that simulates falling rain, you can use the [systemSpawnedOnCollision][18] property to add splashes where each raindrop strikes a surface.

- **Event handlers and particle modifiers.** Because they specify behavior declaratively, animations, property controllers, and spawned systems provide easy configuration and high performance for most dynamic behaviors. To create behaviors not possible with these features, you can register event handler or particle modifier blocks that work directly with the bulk particle data SceneKit uses to animate a particle system.

Use the [handle(_:forProperties:handler:)][19] method to modify particle data in response to an event—particle birth, death, or collision. For example, you can use this option to make particles that change color after colliding with another object in the scene.

Use the methods listed in [Modifying Particles Over Time][20] to manage blocks that SceneKit calls for every rendered frame. Your block can modify particle properties in bulk, allowing you to change particle behavior precisely, but at a high risk to rendering performance.

또한 다음 기능을 사용하여 입자 시스템에 동적 동작을 추가하고 시간 경과에 따라 모양을 변경하거나 주위 환경과 상호 작용할 수 있습니다.

- **애니메이션 및 속성 컨트롤러.** 많은 SceneKit 객체와 마찬가지로 SCNParticleSystem 클래스는 [SCNAnimatable][11] 프로토콜을 따르기때문에 암시적으로 또는 명시적으로 해당 속성의 변경 사항을 애니메이션으로 나타낼 수 있습니다. (애니메이션에 대한 일반적인 배경은 [Animating SceneKit Content][12]를 참조하십시오.) 파티클 시스템의 속성에 대한 변경 사항을 애니메이션으로 적용하면 이러한 변경 사항이 시스템의 모든 입자에 동시에 적용됩니다.

개별 입자에 독립적으로 애니메이션을 적용하려면 [SCNParticlePropertyController][13] 객체를 사용합니다.이 객체는 [CAAnimation][14] 객체를 입자 시스템 속성과 연결합니다. property 컨트롤러를 사용하면 Core Animation 프레임 워크의 기능을 사용하여 시스템의 각 입자에 적용되는 시간에 따른 효과를 만들 수 있습니다. 일반적으로 Core Animation 객체는 시간과 관련하여 속성을 변경하지만 property 컨트롤러를 사용하면 초기 위치에서 입자의 거리와 같은 다른 입력 값을 기반으로 속성을 변경하는 애니메이션을 만들 수도 있습니다.

예를들어, 흰색에서 노란색, 빨간색으로 일련의 색상을 애니메이션하는 [CAKeyframeAnimation][15] 객체와 화염(불꽃)을 시뮬레이트하는 입자 시스템을 생각해보십시오. 이 애니메이션을 입자 시스템의 [particleColor][16] 속성에 첨부하면 결과적인 불꽃 효과는 주어진 순간에 단일 색상을 갖지만 시간이 지남에 따라 색상이 변경됩니다. 대신에 color 속성에 property 컨트롤러를 연결하면 불꽃이 중심에서 가장자리로 다양한 색상이 가능합니다. 각 입자는 흰색으로 시작한 다음 퍼지면서 노란색과 빨간색으로 희미 해집니다.

- **스폰된 입자 시스템.** 다른 SCNParticleSystem 인스턴스를 [추가 파티클 스폰 시스템][17]에 속성들중 하나에 할당하면 SceneKit은 원래 파티클 시스템의 동작을 기반으로 scene에 더 많은 파티클 시스템을 추가합니다. 예를 들어 비가 내리는 것을 시뮬레이션하는 파티클 시스템이있는 경우 [systemSpawnedOnCollision][18] 속성을 사용하여 각 빗방울이 표면에 부딪 치는 위치에 스플래시를 추가 할 수 있습니다.

- **이벤트 처리기 및 입자 수정자.** 선언적으로 동작을 지정하므로 애니메이션, property 컨트롤러 및 spawned 시스템은 대부분의 동적 동작에 대해 손쉬운 구성과 고성능을 제공합니다. 이러한 기능으로는 불가능한 동작을 생성하기 위해, SceneKit이 파티클 시스템에 애니메이션을 적용 할 때 사용하는 대량 입자 데이터와 직접 작동하는 이벤트 핸들러 또는 입자 수정자 블록을 등록 할 수 있습니다.

이벤트 입자의 출생, 사망 또는 충돌에 대한 응답으로 입자 데이터를 수정하려면 [handle(_:forProperties:handler:)][19] 메서드를 사용합니다. 예를들어 이 옵션을 사용하면 장면의 다른 오브젝트와 충돌 한 후 색상이 바뀌는 입자를 만들 수 있습니다.

SceneKit이 모든 렌더링 된 프레임에 대해 호출하는 블록을 관리하려면 [시간에 따라 입자 수정하기][20]에 나열된 방법을 사용하십시오. 블록은 입자 속성을 일괄적으로 수정할 수 있으므로 파티클 동작을 정확하게 변경할 수 있지만 렌더링 성능에 위험이 따릅니다.

<br/>

## Use the Xcode Particle System Editor to Experiment with Particle Systems
In most cases, you don’t need to configure a particle system directly in your app or game. Instead, you use Xcode to configure a particle system’s properties. As you change the behavior of the particle system, Xcode immediately provides an updated visual effect. When complete, Xcode archives the configured system into a file, which you can then include with your project’s bundle resources. Then, at runtime, your game uses this archive to instantiate a new particle system.

Using Xcode to create your particle systems has a few important advantages:
- You can easily learn the capabilities of the particle system class.
- You can experiment quickly with new particle effects and see the results immediately.
- You separate the task of designing a particle effect from the programming task of using it. Your artists can work on new particle effects independent of your game code.
- You can attach a particle system to a node in the Xcode scene editor to preview the particle system in your scene.

To load a particle system from a file you created with Xcode, use the [init(named:inDirectory:)][21] method.

대부분의 경우, 앱이나 게임에서 입자 시스템을 직접 구성 할 필요가 없습니다. 대신 Xcode를 사용하여 입자 시스템의 속성을 구성합니다. 파티클 시스템의 동작을 변경하면 Xcode에서 즉시 업데이트 된 시각적 효과를 제공합니다. 작업이 완료되면 Xcode는 구성된 시스템을 파일로 저장하고 프로젝트의 번들 리소스에 포함시킵니다. 그런다음 런타임때, 게임에서 이 아카이브를 사용하여 새 입자 시스템을 인스턴스화합니다.

Xcode를 사용하여 입자 시스템을 만드는 데는 몇 가지 중요한 이점이 있습니다.
- 파티클 시스템 클래스의 기능을 쉽게 배울 수 있습니다.
- 새로운 입자 효과로 빠르게 실험하고 결과를 즉시 볼 수 있습니다.
- 입자 효과를 디자인하는 작업을 프로그래밍 작업과 분리합니다. 아티스트는 게임 코드와 상관없이 새로운 입자 효과를 사용할 수 있습니다.
- Xcode scene 편집기의 노드에 파티클 시스템을 연결하여 장면에서 파티클 시스템을 미리 볼 수 있습니다.

Xcode로 생성한 파일로부터 파티클 시스템을 로드하려면 [init(named:inDirectory:)][21] 메소드를 사용하십시오.


[Apple Documents][apple]



[1]: https://translate.google.com/translate?hl=ko&sl=en&u=https://en.wikipedia.org/wiki/Particle_system&prev=search
[2]: https://developer.apple.com/documentation/scenekit/scnparticlesystem/1522857-birthrate
[3]: https://developer.apple.com/documentation/scenekit/scnparticlesystem/1523575-particlelifespan
[4]: https://developer.apple.com/documentation/scenekit/scnparticlesystem/1522737-emittershape
[5]: https://developer.apple.com/documentation/scenekit/scnparticlesystem/1523998-emissionduration
[6]: https://developer.apple.com/documentation/scenekit/scnparticlesystem/1522716-particlesizevariation
[7]: https://developer.apple.com/documentation/scenekit/scnparticlesystem/1523508-particlesize
[8]: https://developer.apple.com/documentation/scenekit/scnparticlesystem/1523516-collidernodes
[9]: https://developer.apple.com/documentation/scenekit/scnscene/1522643-physicsworld
[10]: /01_iOS/SceneKit/Physics_Simulation/SCNPhysicsField.md
[11]: /01_iOS/SceneKit/Animation/SCNAnimatable.md
[12]: /01_iOS/SceneKit/Animation/Animating_SceneKit_Content.md
[13]: /01_iOS/SceneKit/SCNParticlePropertyController.md
[14]: /01_iOS/Core_Animation/CAAnimation.md
[15]: /01_iOS/Core_Animation/CAKeyframeAnimation.md
[16]: https://developer.apple.com/documentation/scenekit/scnparticlesystem/1523248-particlecolor
[17]: https://developer.apple.com/documentation/scenekit/scnparticlesystem#1655731
[18]: https://developer.apple.com/documentation/scenekit/scnparticlesystem/1524068-systemspawnedoncollision
[19]: https://developer.apple.com/documentation/scenekit/scnparticlesystem/1523251-handle
[20]: https://developer.apple.com/documentation/scenekit/scnparticlesystem#1655867
[21]: https://developer.apple.com/documentation/scenekit/scnparticlesystem/1522772-init
[apple]: https://developer.apple.com/documentation/scenekit/scnparticlesystem
