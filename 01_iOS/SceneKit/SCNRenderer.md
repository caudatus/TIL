# SCNRenderer
A renderer for displaying a SceneKit scene in an an existing Metal workflow or OpenGL context.

기존의 Metal 워크 플로우 또는 OpenGL 컨텍스트에서 SceneKit scene을 표시하기위한 렌더러.

## Overview
Use this class when you want to add content rendered by SceneKit to an app that already renders other content by using Metal or OpenGL or OpenGL ES directly. To provide content for a SceneKit renderer, assign a [SCNScene][1] object to its [scene][2] property.

For additional important methods and properties for working with SceneKit renderers, see [SCNSceneRenderer][3].

Metal 또는 OpenGL 또는 OpenGL ES를 사용하여 다른 컨텐츠를 이미 렌더링 한 응용 프로그램에 SceneKit으로 렌더링 된 컨텐츠를 추가하려는 경우 이 클래스를 사용하십시오. SceneKit 렌더러에 content를 제공하려면 [scene][2] 속성에 [SCNScene][1] 객체를 할당합니다.

SceneKit 렌더러를 사용하기위한 중요한 메서드 및 속성에 대해서는 [SCNSceneRenderer][3]를 참조하십시오.

[Apple Documents][apple]



[1]: /01_iOS/SceneKit/SCNScene.md
[2]: https://developer.apple.com/documentation/scenekit/scnrenderer/1518400-scene
[3]: /01_iOS/SceneKit/SCNSceneRenderer/SCNSceneRenderer.md
[apple]: https://developer.apple.com/documentation/scenekit/scnrenderer
