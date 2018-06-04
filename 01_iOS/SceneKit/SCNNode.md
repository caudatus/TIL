# SCNNode
A structural element of a scene graph, representing a position and transform in a 3D coordinate space, to which you can attach geometry, lights, cameras, or other displayable content.

geometry, lights, cameras 또는 기타 표시 가능한 객체(컨텐츠)를 표시(add)할 수 있는 3D 좌표 공간에서 위치와 변형을 나타내는 scene 그래프의 구조적 요소입니다.

## Overview
An SCNNode object by itself has no visible content when the scene containing it is rendered—it represents only a coordinate space transform (position, orientation, and scale) relative to its parent node. To construct a scene, you use a hierarchy of nodes to create its structure, then add lights, cameras, and geometry to nodes to create visible content.

SCNNode 객체 자체로는 scene을 포함하는 장면이 렌더링 될 때 보이지 않습니다. 즉, 부모 노드에 상대적인 좌표 공간 변환(위치, 방향 및 비율)만 나타냅니다. scene을 구성하려면 노드 계층 구조를 사용하여 구조를 만든 다음 lights, cameras 및 geometry를 해당 노드에 추가하여 눈에 보이게 컨텐츠를 만들수 있습니다.

## Nodes Determine the Structure of a Scene
The hierarchy of nodes, or scene graph, in a scene defines both the organization of its contents and your ability to present and manipulate those contents using SceneKit. You may create a node hierarchy programmatically using SceneKit, load one from a file created using 3D authoring tools, or combine the two approaches. SceneKit provides many utilities for organizing and searching the scene graph—for details, see the methods in [Managing the Node Hierarchy][1] and [Searching the Node Hierarchy][2].

The [rootNode][3] object in a scene defines the coordinate system of the world rendered by SceneKit. Each child node you add to this root node creates its own coordinate system, which is in turn inherited by its own children. You determine the transformation between coordinate systems using the node’s [position][4], [rotation][5], and [scale][6] properties properties (or directly using its [transform][7] property).

You use a hierarchy of nodes and transformations to model the contents of your scene in a way that suits the needs of your app. For example, if your app presents an animated view of a solar system, you can construct a node hierarchy that models celestial bodies relative to one another: Each planet can be a node, with its orbit and its current position in that orbit defined in the coordinate system of the sun. A planet node defines its own coordinate space, useful both for specifying the planet’s rotation and the orbits of its moons (each of which is a child node of its planet). With this scene hierarchy, you can easily add realistic animation to the scene—animating both the revolution of a moon around its planet and the planet around the sun will combine the animations so that the moon follows the planet.

scene의 노드 계층구조 또는 scene 그래프는 contents의 구성과 SceneKit을 사용하여 contents를 표현하고 조작 할 수 있는 능력을 정의합니다. SceneKit을 사용하여 프로그래밍 방식(수동)으로 노드 계층을 만들거나 3D 저작 도구를 사용하여 만든 파일에서 노드 계층을 로드하거나 두 가지 방법을 함께 사용할 수 있습니다. SceneKit은 scene 그래프를 구성하고 검색하는 많은 유틸리티를 제공합니다. 자세한 내용은 [Managing the Node Hierarchy][1] 및 [Searching the Node Hierarchy][2]의 메소드를 참조하십시오.

scene의 [rootNode][3] 객체는 SceneKit에 의해 렌더링 된 세계의 좌표계를 정의합니다. 이 루트 노드에 추가하는 각 자식 노드는 고유 한 좌표계를 만들고 차례대로 자체 자식에 상속됩니다. 노드의 [위치][4], [회전][5] 및 [배율][6] property를 사용하여 (또는 해당 [transform][7] property를 직접 사용하여) 좌표계 간의 변환을 결정합니다.

노드의 계층 구조와 변환을 사용하여 앱의 요구에 맞는 방식으로 scene의 컨텐츠를 모델링합니다. 예를 들어, 앱에서 태양계의 애니메이션보기를 제공하면 서로 관련하여 천체를 모델링하는 노드 계층 구조를 구성 할 수 있습니다. 각 행성은 태양의 좌표시스템에서 상대적인 궤도와 그 궤도의 위치를 가지는 하나의 노드가 될 수 있습니다. 행성 노드는 행성의 회전과 달의 궤도 (각 행성의 자식 노드)를 지정하는 데 유용한 자체 좌표 공간을 정의합니다. 이 scene 계층 구조를 사용하면 사실적인 애니메이션을 scene에 손쉽게 추가 할 수 있습니다. - 부모 행성 주위를 도는 달의 공전과 태양의 주위를 도는 부모행성의 애니메이션을 조합하면 공전하는 부모행성을 따르는 달을 구현할 수 있습니다.

## A Node’s Attachments Define Visual Content and Behavior
To add physics-based behaviors and special effects to SceneKit content, use other types of node attachments. For example, an [SCNPhysicsBody][8] object defines a node’s characteristics for physics simulation, and an [SCNPhysicsField][9] object applies forces to physics bodies in an area around the node. An [SCNParticleSystem][10] object attached to a node renders particle effects such as fire, rain, or falling leaves in the space defined by a node.

To improve performance, SceneKit can share attachments between multiple nodes. For example, in a racing game that includes many identical cars, the scene graph would contain many nodes—one to position and animate each car—but all car nodes would reference the same geometry object.

SceneKit 컨텐츠에 물리 기반 행동과 특수 효과를 추가하려면 다른 유형의 노드 첨부객체를 사용하십시오. 예를 들어, [SCNPhysicsBody][8] 객체는 물리 시뮬레이션을 위한 노드의 특성을 정의하고, [SCNPhysicsField][9] 객체는 노드 주변 영역안의 물리적 구현 객체에 작용하는 힘을 나타냅니다. 노드에 부착 된 [SCNParticleSystem][10] 객체는 노드가 정의한 공간에 화재, 비 또는 낙엽과 같은 입자 효과를 렌더링합니다.

성능을 향상시키기 위해 SceneKit은 여러 노드간에 첨부된 객체를 공유 할 수 있습니다. 예를 들어, 많은 동일한 자동차를 포함하는 레이싱 게임에서 scene 그래프는 많은 노드를 포함 할 것입니다. 각 자동차는 다른 위치와 다른 애니메이션을 적용하지만 모든 자동차는 동일한 geometry 객체를 참조합니다.


[Apple Documents][apple]




[1]: https://developer.apple.com/documentation/scenekit/scnnode#1655182
[2]: https://developer.apple.com/documentation/scenekit/scnnode#1655236
[3]: https://developer.apple.com/documentation/scenekit/scnscene/1524029-rootnode
[4]: https://developer.apple.com/documentation/scenekit/scnnode/1408026-position
[5]: https://developer.apple.com/documentation/scenekit/scnnode/1408034-rotation
[6]: https://developer.apple.com/documentation/scenekit/scnnode/1408050-scale
[7]: https://developer.apple.com/documentation/scenekit/scnnode/1407964-transform
[8]: /01_iOS/SceneKit/Physics_Simulation/SCNPhysicsBody.md
[9]: /01_iOS/SceneKit/Physics_Simulation/SCNPhysicsField.md
[10]: /01_iOS/SceneKit/SCNParticleSystem.md
[apple]: https://developer.apple.com/documentation/scenekit/scnnode#1655236
