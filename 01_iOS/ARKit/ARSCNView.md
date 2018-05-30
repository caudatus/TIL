# ARSCNView
A view for displaying AR experiences that augment the camera view with 3D SceneKit content.

3D SceneKit content가 표시되는 카메라 뷰의 품질을 높여 AR 경험을 표시하는 뷰

## Overview
The ARSCNView class provides the easiest way to create augmented reality experiences that blend virtual 3D content with a device camera view of the real world. When you run the view's provided ARSession object:

- The view automatically renders the live video feed from the device camera as the scene background.

- The world coordinate system of the view's SceneKit scene directly responds to the AR world coordinate system established by the session configuration.

- The view automatically moves its SceneKit camera to match the real-world movement of the device.

Because ARKit automatically matches SceneKit space to the real world, placing a virtual object such that it appears to maintain a real-world position requires only setting that object's SceneKit position appropriately. (See Providing 3D Virtual Content with SceneKit.)

You don't necessarily need to use the ARAnchor class to track positions of objects you add to the scene, but by implementing ARSCNViewDelegate methods, you can add SceneKit content to any anchors that are automatically detected by ARKit.


ARSCNView 클래스는 가상 3D 컨텐츠를 실제 세계의 디바이스 카메라 view와 혼합하는 증강 현실 경험을 생성하는 가장 쉬운 방법을 제공합니다. view의 제공된 [ARSession][1] 객체를 실행할 때 :

- 이 뷰는 디바이스 카메라의 라이브 비디오 피드를 scene 백그라운드로 자동 렌더링합니다.

- 뷰의 SceneKit scene의 월드 좌표계는 세션 구성에 의해 설정된 AR 월드 좌표계에 직접 응답합니다.

- 뷰는 자동으로 SceneKit 카메라를 움직여 실제 세계 디바이스의 움직임과 일치시킵니다.

ARKit은 자동으로 SceneKit 공간을 실제 세계와 일치시키기 때문에 실제 위치를 유지하는 것처럼 보이는 가상 객체를 배치하면 해당 객체의 SceneKit 위치 만 적절히 설정하면됩니다. 자세한 내용은 [Providing 3D Virtual Content with SceneKit.][2]

[ARAnchor][3] 클래스를 사용하여 장면에 추가하는 객체의 위치를 ​​추적 할 필요는 없지만 [ARSCNViewDelegate][4] 메소드를 구현하면 ARKit에 의해 자동으로 감지 된 모든 앵커에 SceneKit 컨텐츠를 추가 할 수 있습니다.

<br/>

## Example
```Swift
@objc func handleTapGesutre(_ sender: UITapGestureRecognizer) {
   guard let sceneView = sender.view as? ARSCNView else {return}
   let touchLocation = sender.location(in: sceneView)
   let hitTestResult = sceneView.hitTest(touchLocation, types: .existingPlaneUsingExtent)
}
```


[Apple Documents][apple]




[1]: ./ARSession.md
[2]: https://developer.apple.com/documentation/arkit/arscnview/providing_3d_virtual_content_with_scenekit
[3]: ./ARAnchor.md
[4]: ./ARSCNViewDelegate.md
[apple]: https://developer.apple.com/documentation/arkit/arscnview
