# SCNScene
A container for the node hierarchy and global properties that together form a displayable 3D scene.

표시 가능한 3D scene을 함께 구성하는 노드 계층 구조 및 전역 속성에 대한 컨테이너입니다.

## Overview
To display 3D content with SceneKit, you create a scene containing a hierarchy of the nodes and attributes that together represent your visual elements. Typically, you build your assets in a 3D visual editor, then assemble them into a scene using Xcode’s SceneKit Scene Editor, ready for SceneKit to render.

SceneKit을 사용하여 3D 컨텐츠를 표시하려면 시각적 요소를 함께 나타내는 노드 및 속성의 계층을 포함하는 scene을 생성해야합니다. 일반적으로 3D 비주얼 편집기에서 애셋을 빌드 한 다음 Xcode의 SceneKit Scene Editor를 사용하여 scene으로 모아(종합하여)서 SceneKit에서 렌더링 할 준비를 합니다.

<img src="/image/scnscene.png">

To display your scene, you need to load it at runtime, then set it as the scene property of an [SCNView][1]:

scene을 표시하려면 런타임에 장면을 로드 한 다음 [SCNView][1]의 scene 속성으로 설정해야합니다.

```Swift
guard let myScene = SCNScene(named: "MyScene")
    else { fatalError("Unable to load scene file.") }
scnView.scene = myScene // Your app's SCNView
```

## Creating a Scene
The simplest way to create a scene is through Xcode’s SceneKit Scene Editor. Start by importing one or more assets from a 3D editor, such as Blender. Then you adjust the positions and attributes of the assets, and set global scene properties, such as lighting environment, to compose your scene. The scene editor creates a .scn file, which you save to a .scnassets folder in the app bundle. When you build your project, Xcode optimizes the scene file for your target platform.

scene을 만드는 가장 간단한 방법은 Xcode의 SceneKit Scene Editor를 이용하는 것입니다. 먼저 Blender와 같은 3D 편집기에서 하나 이상의 애셋을 가져옵니다. 그런 다음 에셋의 위치와 속성을 조정하고 조명 환경과 같은 전역 장면 속성을 설정하여 장면을 구성합니다. 장면 편집기는 .scn 파일을 만듭니다. 이 파일은 응용 프로그램 번들의 .scnassets 폴더에 저장됩니다. 프로젝트를 빌드 할 때 Xcode는 대상 플랫폼의 scene 파일을 최적화합니다.


[Apple Documents][apple]



[1]: /01_iOS/SceneKit/SCNView.md
[apple]: https://developer.apple.com/documentation/scenekit/scnscene
