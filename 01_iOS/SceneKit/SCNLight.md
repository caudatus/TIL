# SCNLight
A light source that can be attached to a node to illuminate the scene.

scene에 빛을 비추기 위해 노드에 부착 할 수있는 광원.

## Overview
You illuminate your scene by attaching lights to SCNNode objects using their light property.

You set a light’s type using its type property. Depending on a light’s type, its position and direction may affect its behavior—you control the light’s position and direction through the node that the light is attached to. The direction of a light, if applicable to its type, is along the negative z-axis of its node’s local coordinate system.

A light’s other properties affect how it illuminates a scene. All lights have a color property, which interacts with SCNMaterial objects to produce the pixel colors in a rendered scene. Other properties, such as attenuation, shadowing, and spot angle, can affect the behavior of certain types of lights.

The number and type of lights in a scene is a key factor in SceneKit’s rendering performance. For efficient rendering, follow these tips:

- Use SceneKit lights only for dynamic light sources or lights that affect moving objects. For statically lit portions of your scene, create a light map texture in an external 3D authoring tool (also known as baked lighting) and apply it to objects in the scene using the multiply material property.

- Minimize the number of lights on each element of the scene. You can achieve most common lighting effects using no more than three lights, and you only need a single ambient light source. SceneKit only uses up to eight light sources per node when rendering, ignoring any additional lights. If you set the attenuationEndDistance property on a spotlight or omnidirectional light to limit its area of effect, SceneKit ignores the light (and its performance cost) when rendering objects outside that area. You can also use the categoryBitMask property to choose which nodes are illuminated by a light.

[SCNode][1]객체의 [light][2] 속성을 사용하여 lights를 연결하여 scene을 밝게합니다.

[type][3] property를 사용하여 light의 유형을 설정합니다. light의 유형에 따라 위치와 방향이 동작에 영향을 줄 수 있습니다. light가 부착 된 노드를 통해 라이트의 위치와 방향을 제어 할 수 있습니다. 빛의 방향은 해당 유형에 적용 할 수있는 경우 해당 노드의 로컬 좌표계의 음의 z 축을 따릅니다.

light 객체의 다른 properties는 scene을 비추는 방법에 영향을 줍니다. 모든 light 객체에는 [SCNMaterial][4] 객체와 상호 작용하여 렌더링 된 장면에서 픽셀 색상을 생성하는 [color][5] 속성이 있습니다. 감쇠(가늘게 됨), 쉐도잉 및 spot angle과 같은 다른 properties는 특정 유형의 light동작에 영향을 줄 수 있습니다.

scene의 조명 수와 타입은 SceneKit의 렌더링 성능에 중요한 요소입니다. 효율적인 렌더링을 위해 다음 팁을 따르십시오.

- 동적인 광원이나 움직이는 물체에 영향을주는 light에만 SceneKit light 객체를 사용하십시오. 정적으로 조명 된 부분의 장면에서는 외부 3D 제작 도구 (baked lighting이라고도 함)에서 light map texture를 만들고 이를 [multiply][6] material property 사용하여 scene의 객체에 적용합니다.

- scene의 각 요소에 대한 light 수를 최소화하십시오. 대부분의 조명 효과는 최대 3 개의 조명을 사용하여 얻을 수 있으며 주변 조명을 하나만 필요로합니다. SceneKit은 렌더링 할 때 노드 당 최대 8 개의 광원만을 사용하며 추가 조명은 무시합니다. spotlight 또는 omnidirectional light의 [attenuationEndDistance][7] property를 설정하여 효과의 범위를 제한하면 SceneKit은 해당 영역 외부의 객체를 렌더링 할 때 광원 및 해당 성능 비용을 무시합니다. [categoryBitMask property][8] 사용하여 조명에 의해 조명되는 노드를 선택할 수도 있습니다.

[Apple Documents][apple]


[1]: ./SCNNode.md
[2]: https://developer.apple.com/documentation/scenekit/scnnode/1408004-light
[3]: https://developer.apple.com/documentation/scenekit/scnlight/1522919-type
[4]: ./SCNMaterial/SCNMaterial.md
[5]: https://developer.apple.com/documentation/scenekit/scnlight/1523627-color
[6]: https://developer.apple.com/documentation/scenekit/scnmaterial/1462575-multiply
[7]: https://developer.apple.com/documentation/scenekit/scnlight/1524140-attenuationenddistance
[8]: https://developer.apple.com/documentation/scenekit/scnlight/1523669-categorybitmask
[apple]: https://developer.apple.com/documentation/scenekit/scnlight
