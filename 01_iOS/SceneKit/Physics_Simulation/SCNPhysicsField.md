# SCNPhysicsField
An object that applies forces, such as gravitation, electromagnetism, and turbulence, to physics bodies within a certain area of effect.

중력, 전자 기류 및 난류와 같은 힘을 특정 영역 내에서 물리 구조에 적용하는 객체입니다.

## Overview
You can create many types of field effects, such as gravitation, electromagnetism, and turbulence. To add a field effect to a scene, you create a physics field of the type you want to use and then attach it to the physicsField property of a node in the scene.

Physics fields can affect both [SCNPhysicsBody][1] objects and the particles spawned by [SCNParticleSystem][2] objects.

중력, 전자기 및 난기류와 같은 다양한 필드 효과를 만들 수 있습니다. scene에 필드 효과를 추가하려면 사용할 유형의 physics field를 만든 다음 scene의 노드의 physicsField 속성에 추가합니다.

피직스 필드는 [SCNPhysicsBody][1] 객체와 [SCNParticleSystem][2] 객체에 의해 생성 된 입자 모두에 영향을 줄 수 있습니다.

[Apple Documents][apple]


[1]: /01_iOS/SceneKit/Physics_Simulation/SCNPhysicsBody.md
[2]: /01_iOS/SceneKit/SCNParticleSystem.md
[apple]: https://developer.apple.com/documentation/scenekit/scnphysicsfield
