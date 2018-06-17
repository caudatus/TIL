# SCNLayer
A Core Animation layer that renders a SceneKit scene as its content.

SceneKit scene을 컨텐츠로써 렌더링하는 Core Animation 레이어입니다.

## Overview
Use this class to integrate 3D content rendered by SceneKit into a user interface composed of Core Animation layers. To provide content for the layer, assign an [SCNScene][1] object to its [scene][2] property.

Most of the methods and properties you use for working with a SceneKit layer are defined by the [SCNSceneRenderer][3] protocol.

이 클래스를 사용하여 SceneKit에서 렌더링 한 3D 컨텐츠를 Core Animation 레이어로 구성된 사용자 인터페이스에 통합합니다. 레이어에 컨텐츠를 제공하려면 [scene][2] 속성에 [SCNScene][1] 객체를 할당합니다.

SceneKit 레이어로 작업 할 때 사용하는 대부분의 메서드 및 속성은 [SCNSceneRenderer][3] 프로토콜에 의해 정의됩니다.

[Apple Documents][apple]


[1]: /01_iOS/SceneKit/SCNScene.md
[2]: https://developer.apple.com/documentation/scenekit/scnlayer/1393188-scene
[3]: /01_iOS/SceneKit/SCNSceneRenderer/SCNSceneRenderer.md
[apple]: https://developer.apple.com/documentation/scenekit/scnlayer
