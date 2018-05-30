# ARSCNViewDelegate
Methods you can implement to mediate the automatic synchronization of SceneKit content with an AR session.

AR 세션에서 SceneKit 컨텐츠의 자동 동기화를 조절하기 위해 구현할 수있는 메소드.

## Overview
Implement this protocol to provide SceneKit content corresponding to ARAnchor objects tracked by the view's AR session, or to manage the view's automatic updating of such content.
This protocol extends the ARSessionObserver protocol, so your session delegate can also implement those methods to respond to changes in session status.

이 프로토콜을 구현하여 view의 AR 세션에 의해 추적 된 [ARAnchor][1] 객체에 해당하는 SceneKit 컨텐트를 제공하거나 해당 컨텐트의 view 자동 업데이트를 관리합니다.
이 프로토콜은 [ARSessionObserver][2] 프로토콜을 확장하므로 session delegate는 이러한 메서드를 구현하여 세션 상태의 변경 내용에 응답 할 수 있습니다.

## Methods
```Swift
func renderer(SCNSceneRenderer, nodeFor: ARAnchor)
//Asks the delegate to provide a SceneKit node corresponding to a newly added anchor.

func renderer(SCNSceneRenderer, didAdd: SCNNode, for: ARAnchor)
//Tells the delegate that a SceneKit node corresponding to a new AR anchor has been added to the scene.

func renderer(SCNSceneRenderer, willUpdate: SCNNode, for: ARAnchor)
//Tells the delegate that a SceneKit node's properties will be updated to match the current state of its corresponding anchor.

func renderer(SCNSceneRenderer, didUpdate: SCNNode, for: ARAnchor)
//Tells the delegate that a SceneKit node's properties have been updated to match the current state of its corresponding anchor.

func renderer(SCNSceneRenderer, didRemove: SCNNode, for: ARAnchor)
//Tells the delegate that the SceneKit node corresponding to a removed AR anchor has been removed from the scene.
```





[Apple Documents][apple]





[1]: ./ARAnchor.md
[2]: ./ARSessionObserver.md
[apple]: https://developer.apple.com/documentation/arkit/arscnviewdelegate
