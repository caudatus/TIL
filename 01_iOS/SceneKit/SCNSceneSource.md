# SCNSceneSource
An object that manages the data-reading tasks associated with loading scene contents from a file or data.

파일이나 데이터에서 scene contents를 로드하는 것과 관련된 데이터 읽기 작업을 관리하는 객체입니다.

## Overview
You can also use a scene source to examine the contents of a scene file or to selectively extract certain elements of a scene without keeping the entire scene and all the assets it contains.

SceneKit can read scene contents from a file in a supported format, or from an [NSData][1] object holding the contents of such a file. Supported formats include the following:

| Format | Filename Extension | Supported in |
| :--: | :--: | :--: |
| **Digital Asset Exchange** | .dae | macOS 10.8 and later |
| **Alembic** | .abc | macOS 10.10 and later |
| **SceneKit compressed scene** | .dae or .abc | macOS 10.10 and later, iOS 8.0 and later |
| **SceneKit archive** | .scn | macOS 10.10 and later, iOS 8.0 and later |

When you include a scene file in DAE or Alembic format in your Xcode project, Xcode automatically converts the file to SceneKit’s compressed scene format for use in the built app. The compressed file retains its original .dae or .abc extension.

The SCNSceneSource class can also load SceneKit archive files, which you create in the Xcode scene editor or programmatically by using the [NSKeyedArchiver][2] class to serialize an [SCNScene][3] object and the scene graph it contains.

또한 장면 원본을 사용하여 scene 파일의 내용을 검사하거나 전체 scene과 포함 된 모든 에셋을 유지하지 않고 scene의 특정 요소를 선택적으로 추출 할 수 있습니다.

SceneKit은 지원되는 형식의 파일 또는 해당 파일의 내용을 보유하는 [NSData][1] 객체에서 scene 내용을 읽을 수 있습니다. 지원되는 형식은 다음과 같습니다.

| Format | Filename Extension | Supported in |
| :--: | :--: | :--: |
| **Digital Asset Exchange** | .dae | macOS 10.8 and later |
| **Alembic** | .abc | macOS 10.10 and later |
| **SceneKit compressed scene** | .dae or .abc | macOS 10.10 and later, iOS 8.0 and later |
| **SceneKit archive** | .scn | macOS 10.10 and later, iOS 8.0 and later |

Xcode 프로젝트에 DAE 또는 Alembic 형식의 scene 파일을 포함 시키면 Xcode에서 자동으로 파일을 SceneKit의 compressed scene format으로 변환하여 내장된 응용 프로그램에서 사용합니다. 압축된 파일은 원래 .dae 또는 .abc 확장자를 유지합니다.

SCNSceneSource 클래스는 Xcode scene 편집기에서 생성한 SceneKit archive 파일을 로드하거나 [NSKeyedArchiver][2] 클래스를 사용하여 프로그래밍 방식으로 [SCNScene][3] 객체 및 포함된 scene 그래프를 직렬화 할 수도 있습니다.


## Note
For best results, place scene files that ship in your app bundle in a folder with the .scnassets extension, and place image files referenced as textures from those scenes in an Asset Catalog. Xcode then optimizes the scene and texture resources for best performance on each target device, and prepares your texture resources for delivery features such as App Thinning and On-Demand Resources.

최상의 결과를 얻으려면 응용 프로그램 번들에 들어있는 씬 파일을 .scnassets 확장자가 있는 폴더에 저장하고 해당 장면의 텍스처로 참조 된 이미지 파일을 Asset 카탈로그에 저장하십시오. 그런 다음 Xcode는 각 대상 장치에서 최고의 성능을 발휘할 수 있도록 scene 및 텍스처 리소스를 최적화하고 App Thinning 및 On-Demand 리소스와 같은 전송 기능을 위해 텍스처 리소스를 준비합니다.




[Apple Documents][apple]



[1]: https://developer.apple.com/documentation/foundation/nsdata
[2]: https://developer.apple.com/documentation/foundation/nskeyedarchiver
[3]: /01_iOS/SceneKit/SCNScene.md
[apple]: https://developer.apple.com/documentation/scenekit/scnscenesource
