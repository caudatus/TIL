# SCNMaterialProperty
A container for the color or texture of one of a material’s visual properties.

머티리얼의 시각적 속성 중 색 또는 질감을 위한 컨테이너 객체입니다.

## Overview
A material has several visual properties that together determine its appearance under lighting and shading. SceneKit renders each pixel in the scene by combining the information from material properties with the locations, intensities, and colors of lights.

A material property’s contents can be either a color, which provides a uniform effect across the surface of a material, or a texture, which SceneKit maps across the surface of a material using texture coordinates provided by the geometry object the material is attached to. A texture, in turn, can come from any of several sources, such as an image object, a URL to an image file, a specially formatted image or set of images for use as a cube map, or even animated content provided by Core Animation, SpriteKit, or AVFoundation—for the full set of options, see the contents property.

머티리얼은 조명 및 음영 처리시 나타나는 모양을 결정하는 여러 가지 시각적 속성을 가지고 있다. SceneKit은 material 속성의 정보를 조명의 위치, 강도 및 색상과 결합하여 장면의 각 픽셀을 렌더링합니다.

material 속성의 contents는 머티리얼의 표면 전체에 걸쳐 균일 한 효과를주는 색상이거나 텍스처가 첨부 된 기하학 객체에 의해 제공되는 텍스처 좌표를 사용하여 머티리얼의 표면 전체에 매핑되는 텍스처 일 수 있습니다. 텍스처는 이미지 객체, 이미지 파일에 대한 URL, 큐브 맵으로 사용하기 위해 특수하게 포맷 된 이미지 또는 이미지 세트 또는 Core Animation, SpriteKit, AVFoundation에서 제공하는 애니메이션 컨텐츠와 같은 여러 소스 중 하나에서 가져올 수 있습니다. 자세한 내용은 [contents][content] 속성을 참조하십시오.

> **Note**
Typically, you associate texture images with materials when creating 3D assets with third-party authoring tools, and the scene files containing those assets reference external image files. For best results when shipping assets in your app bundle, place scene files in a folder with the .scnassets extension, and place image files referenced as textures from those scenes in an Asset Catalog.
Xcode then optimizes the scene and texture resources for best performance on each target device, and prepares your texture resources for delivery features such as App Thinning and On-Demand Resources.


일반적으로 타사 저작 도구를 사용하여 3D 에셋을 만들 때 재질과 텍스처 이미지를 연결하고 이러한 에셋이 포함 된 scene 파일은 외부 이미지 파일을 참조합니다. 앱 번들에 애셋을 전송할 때 최상의 결과를 얻으려면 .scnassets 확장자가있는 폴더에 scene 파일을 배치하고 해당 scene의 텍스처로 참조 된 이미지 파일을 애셋 카탈로그에 배치하십시오.
그런 다음 Xcode는 각 디바이스에서 최고의 성능을 발휘할 수 있도록 장면 및 텍스처 리소스를 최적화하고 App Thinning 및 On-Demand 리소스와 같은 전송 기능을 위해 텍스처 리소스를 준비합니다.



[Apple Documents][apple]


[content]: https://developer.apple.com/documentation/scenekit/scnmaterialproperty/1395372-contents
[apple]: https://developer.apple.com/documentation/scenekit/scnmaterialproperty
