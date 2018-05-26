# SCNMaterial.LightingModel
Constants specifying the lighting and shading algorithm to use for rendering a material.

material의 rendering에 사용하는 조명, 음영 알고리즘을 지정하는 정수입니다.

## Type Properties
- **static let [blinn][bli]: SCNMaterial.LightingModel**
  - Shading that incorporates ambient, diffuse, and specular properties, where specular highlights are calculated using the Blinn-Phong formula.

- **static let [constant][cons]: SCNMaterial.LightingModel**
  - Uniform shading that incorporates ambient lighting only.

- **static let [lambert][lam]: SCNMaterial.LightingModel**
  - Shading that incorporates ambient and diffuse properties only.

- **static let [phong][pho]: SCNMaterial.LightingModel**
  - Shading that incorporates ambient, diffuse, and specular properties, where specular highlights are calculated using the Phong formula.

- **static let [physicallyBased][phy]: SCNMaterial.LightingModel**
  - Shading based on a realistic abstraction of physical lights and materials.

[Apple Documents][apple]

[bli]: https://developer.apple.com/documentation/scenekit/scnmaterial.lightingmodel/1462514-blinn
[cons]:https://developer.apple.com/documentation/scenekit/scnmaterial.lightingmodel/1462538-constant
[lam]: https://developer.apple.com/documentation/scenekit/scnmaterial.lightingmodel/1462529-lambert
[pho]: https://developer.apple.com/documentation/scenekit/scnmaterial.lightingmodel/1462582-phong
[phy]: https://developer.apple.com/documentation/scenekit/scnmaterial.lightingmodel/1640553-physicallybased
[apple]: https://developer.apple.com/documentation/scenekit/scnmaterial.lightingmodel
