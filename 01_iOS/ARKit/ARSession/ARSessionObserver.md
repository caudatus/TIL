# ARSessionObserver
Methods you can implement to respond to changes in the state of an AR session.

AR 세션의 상태 변화에 대응하기 위해 구현할 수있는 메소드.

## Overview
This protocol defines optional methods common to the ARSessionDelegate, ARSCNViewDelegate, and ARSKViewDelegate protocols. You can implement this protocol's methods when adopting one of those protocols.

이 프로토콜은 [ARSessionDelegate][1], [ARSCNViewDelegate][2] 및 ARSKViewDelegate 프로토콜에 공통적인 선택적 메소드를 정의합니다. 이러한 프로토콜 중 하나를 채택할때 이 프로토콜의 메소드를 구현할 수 있습니다.

```Swift
func session(ARSession, cameraDidChangeTrackingState: ARCamera)
//Informs the delegate of changes to the quality of ARKit's device position tracking.
```

[Apple Documents][apple]



[1]: ./ARSessionDelegate.md
[2]: ../ARSCNViewDelegate.md
[apple]: https://developer.apple.com/documentation/arkit/arsessionobserver
