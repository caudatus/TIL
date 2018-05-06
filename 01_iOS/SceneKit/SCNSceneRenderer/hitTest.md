# hitTest
Searches the renderer’s scene for objects corresponding to a point in the rendered image.

SCNView, SCNLayer, and SCNRenderer 안에서 주어진 포인트(좌표)에 해당하는 오브젝트가 있는지 체크한다.

```Swift
func hitTest(_ point: CGPoint,
     options: [SCNHitTestOption : Any]? = nil) -> [SCNHitTestResult]
```

## Example
```Swift
@objc func handleTapGesture(_ sender: UITapGestureRecognizer) {
   let sceneViewTappedOn = sender.view as! SCNView
   let touchCoordinates = sender.location(in: sceneViewTappedOn)
   let hitTest = sceneViewTappedOn.hitTest(touchCoordinates)

   if hitTest.isEmpty {
      print("didn't touch anything")
   } else {
      print(hitTest)
   }
}
```

[Apple Documents][apple]

[apple]: https://developer.apple.com/documentation/scenekit/scnscenerenderer/1522929-hittest
