# SCNGeometry
A three-dimensional shape (also called a model or mesh) that can be displayed in a scene, with attached materials that define its appearance.

외양을 정의하는 materials 객체와 함께 scene에 표시 할 수있는 3 차원 형태 (model 또는 mesh라고도 함).

</br>

## Overview
In SceneKit, geometries attached to SCNNode objects form the visible elements of a scene, and SCNMaterial objects attached to a geometry determine its appearance.

SceneKit에서, [SCNNode][scnnode] 객체에 연결된 geometries는 scene에서 보이게 하는, 나타나게 하는 요소를 형성하고, geometry에 연결된 [SCNMaterial][material] 객체는 그 모양을 결정합니다.

</br>

## Working with Geometry Objects
**You control a geometry’s appearance in a scene with nodes and materials.** A geometry object provides only the form of a visible object rendered by SceneKit. You specify color and texture for a geometry’s surface, control how it responds to light, and add special effects by attaching materials (for details, see the methods in Managing a Geometry’s Materials). You position and orient a geometry in a scene by attaching it to an SCNNode object. Multiple nodes can reference the same geometry object, allowing it to appear at different positions in a scene.

**You can easily copy geometries and change their materials.** A geometry object manages the association between immutable vertex data and a mutable assignment of materials. To make a geometry appear more than once in the same scene with a different set of materials, use its inherited copy() method. The copy shares the underlying vertex data of the original, but can be assigned materials independently. You can thus make many copies of a geometry without incurring a significant cost to rendering performance.

**You can animate a geometry object.** The vertex data associated with a geometry is immutable, but SceneKit provides several ways to animate geometry. You can use a SCNMorpher or SCNSkinner object to deform a geometry’s surface, or run animations created in an external 3D authoring tool and loaded from a scene file. You can also use methods in the SCNShadable protocol to add custom GLSL shader programs that alter SceneKit’s rendering of a geometry.


**scene에서 nodes와 materials을 통해 geometry의 모양을 제어할 수 있습니다.** geometry 객체는 SceneKit에 의해 렌더링되는 화면상에 보이는 객체의 형태만을 제공합니다. geometry 표면의 색상과 텍스처를 지정할 수 있고, 조명(빛)에 반응하는 방법을 제어할 수 있고, materials 객체를 add하여 특수 효과를 추가할 수 있습니다. (자세한 내용은 [Managing a Geometry’s Materials][manage] methods 참조). scene의 geometry의 위치와 방향을 SCNNode 객체에 연결하여 지정할 수 있습니다. 여러 노드가 동일한 geometry 객체를 참조 할 수 있으므로 scene의 다른 위치에 나타낼 수 있습니다.

**geometries를 복사하고 materials을 변경하는 것은 쉽습니다.** geometry 객체는 변경 불가능한 정점(도형의 꼭지점) 데이터와 변경 가능한 materials 간의 관계를 관리합니다. 서로 다른 materials 세트를 사용하여 동일한 장면에서 geometry 두 번 이상 표시하려면 상속 된 copy () 메서드를 사용합니다. 복사본은 원본의 기본 꼭지점 데이터(모양, 형태)를 공유하지만 materials을 독립적으로 할당 할 수 있습니다. 따라서 렌더링에 상당한 물리 메모리를 쓰지 않고 geometry의 많은 복사본을 만들 수 있습니다.

**geometry 오브젝트를 애니메이트 할 수 있습니다.** geometry와 관련된 버텍스 데이터는 변경할 수 없지만, SceneKit은 geometry를 애니메이트하는 몇 가지 방법을 제공합니다. [SCNMorpher][scnmorpher] 또는 [SCNSkinner][scnskinner] 객체를 사용하여 geometry의 표면을 변형하거나 외부 3D 제작 도구에서 생성되고 scene파일에서 로드 된 애니메이션을 실행할 수 있습니다. 또한 [SCNShadable][scnshadable] 프로토콜의 메소드를 사용하여 SceneKit의 geometry 렌더링을 변경하는 사용자 정의 GLSL 셰이더 프로그램을 추가 할 수 있습니다.


[Apple Documents][apple]


[scnnode]: /01_iOS/SceneKit/SCNNode.md
[material]: /01_iOS/SceneKit/SCNMaterial/SCNMaterial.md
[manage]: https://developer.apple.com/documentation/scenekit/scngeometry#1655143
[scnmorpher]: /01_iOS/SceneKit/SCNMorpher.md
[scnskinner]: /01_iOS/SceneKit/SCNSkinner.md
[scnshadable]: /01_iOS/SceneKit/SCNShadable.md
[apple]: https://developer.apple.com/documentation/scenekit/scngeometry#1655143
