# SCNMaterial
A set of shading attributes that define the appearance of a geometry's surface when rendered.

렌더링 될 때 지오메트리 표면의 모양을 정의하는 음영 속성 집합이다.

## Overview
When you create a material, you define a collection of visual attributes and their options, which you can then reuse for multiple geometries in a scene.

A material has several visual properties, each of which defines a different part of SceneKit’s lighting and shading process. Each visual property is an instance of the SCNMaterialProperty class that provides a solid color, texture, or other 2D content for that aspect of SceneKit’s rendering. The material’s lightingModel property then determines the formula SceneKit uses to combine the visual properties with the lights in the scene to produce the final color for each pixel in the rendered scene. For more details on the rendering process, see SCNMaterial.LightingModel.

You attach one or more materials to an instance of the SCNGeometry class using its firstMaterial or materials property. Multiple geometries can reference the same material. In this case, changing the attributes of the material changes the appearance of every geometry that uses it.

머티리얼을 만들 때 시각적 속성 및 옵션의 컬렉션을 정의한 다음,
scene안에서 여러 geometry에 재사용 할 수 있다.

머티리얼에는 여러 가지 시각적 속성이 있다. 각 속성은 SceneKit의 조명 및 음영 처리의 다른 부분을 정의한다. 각 시각적 속성은 [SCNMaterialProperty][scnmaterialproperty] 클래스의 인스턴스로 SceneKit의 렌더링 측면에 대한 단색, 텍스처 또는 기타 2D 내용을 제공한다. 그런 다음 머티리얼의 [lightingModel][lighting] 속성은 SceneKit이 시각적 속성을 장면의 광원과 결합하여 렌더링 된 장면의 각 픽셀에 대한 최종 색상을 생성하는 데 사용하는 수식을 결정한다. 렌더링 프로세스에 대한 자세한 내용은 [SCNMaterial.LightingModel][scn.light]을 참조하시오.

[firstMaterial][first] 또는 [materials][material] 속성을 사용하여 하나 이상의 재질을 [SCNGeometry][scngeometry] 클래스의 인스턴스에 연결합니다. 여러 geometry는 동일한 머티리얼을 참조 할 수 있습니다. 이 경우 머티리얼의 속성을 변경하면 해당 머티리얼을 사용하는 모든 geometry 모양이 변경됩니다.


[Apple Documents][apple]


[scnmaterialproperty]: https://developer.apple.com/documentation/scenekit/scnmaterialproperty
[lighting]: https://developer.apple.com/documentation/scenekit/scnmaterial/1462518-lightingmodel
[scn.light]: https://developer.apple.com/documentation/scenekit/scnmaterial.lightingmodel
[scngeometry]: https://developer.apple.com/documentation/scenekit/scngeometry
[first]: https://developer.apple.com/documentation/scenekit/scngeometry/1523485-firstmaterial
[material]: https://developer.apple.com/documentation/scenekit/scngeometry/1523472-materials
[apple]: https://developer.apple.com/documentation/scenekit/scnmaterial
