# ARWorldTrackingConfiguration
A configuration that uses the back-facing camera, tracks a device's orientation and position, and detects real-world flat surfaces.

뒷면 카메라를 사용하여 디바이스의 orientation 과 position을 추적하고, 실제 세상의 평평한 면을 감지하는 configuration(구성,배치) 객체

If you enable the planeDetection setting, ARKit analyzes the scene to find real-world horizontal or vertical surfaces. For each plane detected, ARKit automatically adds an ARPlaneAnchor object to the session.

planeDetection을 가능하게 설정하 ARKit은 real-world의 수평면과 수직면을 찾기위해 scene(디바이스 카메라에서 캡쳐된 장면)을 분석,해석 한다. 감지된 각각의 면을, ARKit은 자동으로 session 객체에 ARPlaneAnchor 객체로 저장한다.

## Example
```Swift
override func viewWillAppear(_ animated: Bool) {
   // Create a session configuration
   let configuration = ARWorldTrackingConfiguration()
   configuration.planeDetection = .horizontal

   // Run the view's session
   sceneView.session.run(configuration)
}
```


[Apple Documents][apple]

[apple]: https://developer.apple.com/documentation/arkit/arworldtrackingconfiguration
