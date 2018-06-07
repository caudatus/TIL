# ARSessionDelegate
Methods you can implement to receive captured video frame images and tracking state from an AR session.

캡처 된 비디오 프레임 이미지를 수신하고 AR 세션의 상태를 추적하도록 구현할 수있는 메소드.

## Overview
Implement this protocol if you need to work directly with [ARFrame][1] objects captured by the session or directly follow changes to the session's set of tracked [ARAnchor][2] objects. Typically, you adopt this protocol when building a custom view for displaying AR content—if you display content with SceneKit or SpriteKit, the [ARSCNViewDelegate][3] and ARSKViewDelegate protocols provide similar information and integrate with those technologies.

This protocol extends the [ARSessionObserver][4] protocol, so your session delegate can also implement those methods to respond to changes in session status.

세션에서 캡처 한 [ARFrame][1] 객체로 직접 작업하거나 세션의 추적된 [ARAnchor][2] 객체 세트에 대한 변경 사항을 직접 수행해야하는 경우 이 프로토콜을 구현하십시오. 일반적으로 AR 컨텐츠를 표시하기위한 custom view를 작성할 때 이 프로토콜을 사용합니다. SceneKit 또는 SpriteKit으로 컨텐츠를 표시하면 [ARSCNViewDelegate][3] 및 ARSKViewDelegate 프로토콜이 유사한 정보를 제공하고 해당 기술과 통합됩니다.

이 프로토콜은 [ARSessionObserver][4] 프로토콜을 확장하므로 세션 delegate는 이러한 메서드를 구현하여 세션 상태의 변경 내용에 응답 할 수 있습니다.

[Apple Documents][apple]




[1]: ../ARFrame.md
[2]: ../ARAnchor.md
[3]: ../ARSCNViewDelegate.md
[4]: ./ARSessionObserver.md
[apple]: https://developer.apple.com/documentation/arkit/arsessiondelegate
