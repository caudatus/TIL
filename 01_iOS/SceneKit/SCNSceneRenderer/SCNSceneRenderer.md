# SCNSceneRenderer: Protocol
Methods and properties common to the [SCNView][1], [SCNLayer][2], and [SCNRenderer][3] classes.

[SCNView][1], [SCNLayer][2] 및 [SCNRenderer][3] 클래스에 공통된 메서드 및 속성

## Overview
You use an instance of one of these classes to display a scene and manage SceneKit’s rendering and animation of the scene’s contents.

Typically, you use the [SCNView][1] class to display a scene in a window (or full screen). You can create and configure a SceneKit view programmatically or in Interface Builder. The other renderer classes render SceneKit content in more specialized situations. If your app has a user interface composed of Core Animation layers, you can use the [SCNLayer][2] class to render a scene into a layer. If your app uses Metal or OpenGL for other rendering, you can use the [SCNRenderer][3] class to render SceneKit content with the same Metal device or OpenGL context.

Use the scene property of the view, layer, or renderer to specify the scene to display.

이러한 클래스 중 하나의 인스턴스를 사용하여 scene을 표시하고 scene contents의 SceneKit 렌더링 및 애니메이션을 관리합니다.

일반적으로 [SCNView][1] 클래스를 사용하여 window(또는 전체 화면)에 scene을 표시합니다. 프로그래밍 방식으로 또는 Interface Builder에서 SceneKit 뷰를 만들고 구성 할 수 있습니다. 다른 렌더러 클래스는보다 특수화된 상황에서 SceneKit 컨텐츠를 렌더링합니다. 앱에 Core Animation 레이어로 구성된 사용자 인터페이스가있는 경우 [SCNLayer][2] 클래스를 사용하여 scene을 레이어로 렌더링 할 수 있습니다. 앱이 다른 렌더링을 위해 Metal 또는 OpenGL을 사용하는 경우 [SCNRenderer][3] 클래스를 사용하여 동일한 Metal 장치 또는 OpenGL 컨텍스트로 SceneKit 내용을 렌더링 할 수 있습니다.

뷰, 레이어 또는 렌더러의 scene 속성을 사용하여 표시 할 scene을 지정합니다.

## autoenablesDefaultLighting
A Boolean value that determines whether SceneKit automatically adds lights to a scene.

If this property’s value is false (the default), the only light sources SceneKit uses for rendering a scene are those contained in the scene graph. If you change the value to true, SceneKit automatically adds and places an omnidirectional light source when rendering scenes that contain no lights or only contain ambient lights.

SceneKit이 scene에 조명을 자동으로 추가하는지 여부를 결정하는 Boolean value.

이 property의 값이 false (디폴트)의 경우, SceneKit이 scene의 렌더링에 사용하는 광원은 scene 그래프에 포함되는 광원뿐입니다. 값을 true로 변경하면, 라이트를 포함하지 않거나 앰비언트 라이트만 포함하는 scene을 렌더링 할 때, 전방향 광원을 자동으로 추가하고 배치합니다.

전반향성(Omnidirectional) 혹은 무지향성(Non-directional)은 방향의 범위 기준이 없이 사방에서 빛을 비춘다는 의미이다.

[Apple Documents][apple]



[1]: /01_iOS/SceneKit/SCNView.md
[2]: /01_iOS/SceneKit/SCNLayer.md
[3]: /01_iOS/SceneKit/SCNRenderer.md
[apple]: https://developer.apple.com/documentation/scenekit/scnscenerenderer
