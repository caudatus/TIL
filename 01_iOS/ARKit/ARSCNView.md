# ARSCNView
A view for displaying AR experiences that augment the camera view with 3D SceneKit content.

3D SceneKit content가 표시되는 카메라 뷰의 품질을 높여 AR 경험을 표시하는 뷰

## Example
```Swift
@objc func handleTapGesutre(_ sender: UITapGestureRecognizer) {
   guard let sceneView = sender.view as? ARSCNView else {return}
   let touchLocation = sender.location(in: sceneView)
   let hitTestResult = sceneView.hitTest(touchLocation, types: .existingPlaneUsingExtent)
}
```


[Apple Documents][apple]

[apple]: https://developer.apple.com/documentation/arkit/arscnview
