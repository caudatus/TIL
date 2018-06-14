# SCNParticlePropertyController
An animation for a single property of the individual particles rendered by a particle system.

파티클 시스템에 의해 렌더링 된 개별 입자의 단일 속성에 대한 애니메이션입니다.

## Overview
Use particle property controllers to change the properties of individual particles in an [SCNParticleSystem][1] object over time, with Core Animation semantics. For example, by associating a keyframe animation with a particle system’s color property, you can create a flame effect with particles that change from blue to white to orange as they rise.

A particle property controller animates a property of individual particles rendered by the particle system. By comparison, implicitly or explicitly animating properties of a SCNParticleSystem object affects the system as a whole. Consider the keyframe animation of colors described above—if you apply this animation directly to a particle system instead of using a property controller, all particles rendered by the system change color together instead of each one changing color as it rises.

Core Animation animations in SceneKit typically animate a change to a property as a function of time. By default, property controllers animate a particle property this way. However, by changing the [inputMode][2] property you can also create animations that animate a particle property as a function of distance from a specified node or of the value of another particle property. For example, you can use this option to make particles change color as they speed up and slow down.

For more details about particle systems and particle properties, see [SCNParticleSystem][1].

입자 속성 컨트롤러를 사용하여 [SCNParticleSystem][1] 객체의 개별 입자 속성을 시간 경과에 따라 변경합니다. 예를 들어 키 프레임 애니메이션을 파티클 시스템의 color 속성과 연결하면 입자가 파란색에서 흰색에서 주황색으로 바뀌는 화염 효과를 만들수 있습니다.

입자 속성 컨트롤러는 입자 시스템에 의해 렌더링된 개별 입자의 속성을 애니메이션으로 나타냅니다. 반면, SCNParticleSystem 객체의 암시적 또는 명시적 애니메이션 속성은 시스템 전체에 영향을줍니다. 위에서 설명한 색상의 키 프레임 애니메이션을 고려하십시오. 속성 컨트롤러를 사용하는 대신 애니메이션을 파티클 시스템에 직접 적용하면 시스템에서 렌더링 된 모든 입자가 나타날 때마다 색상이 개별적으로 변하는 대신 모든 입자가 함께 색상이 함께 변경됩니다.

SceneKit의 Core Animation 애니메이션은 일반적으로 시간의 함수로 속성의 변경 사항을 애니메이션으로 만듭니다. 기본적으로 속성 컨트롤러는 입자 속성을 이러한 방식으로 애니메이션화합니다. 그러나 [inputMode][2] 속성을 변경하면 지정된 노드 또는 다른 입자 속성 값과의 거리 함수로 입자 속성에 애니메이션을 적용하는 애니메이션을 만들 수도 있습니다. 예를 들어,이 옵션을 사용하면 파티클의 속도를 높이거나 낮추면서 색상을 변경할 수 있습니다.

입자 시스템 및 입자 속성에 대한 자세한 내용은 [SCNParticleSystem][1]을 참조하십시오.


[Apple Documents][apple]




[1]: ./SCNParticleSystem.md
[2]: https://developer.apple.com/documentation/scenekit/scnparticlepropertycontroller/1522852-inputmode
[apple]: https://developer.apple.com/documentation/scenekit/scnparticlepropertycontroller
