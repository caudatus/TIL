# CABasicAnimation
An object that provides basic, single-keyframe animation capabilities for a layer property.

기본적인 싱글프레임 애니메이션이 가능한 오브젝트

```Swift
let animation = CABasicAnimation(keyPath: "opacity")
animation.fromValue = 0
animation.toValue = 1

let animation = CABasicAnimation(keyPath: "backgroundColor")
animation.fromValue = NSColor.red.cgColor
animation.toValue = NSColor.blue.cgColor

let animation = CABasicAnimation(keyPath: "position")
animation.fromValue = [0, 0]
animation.toValue = [100, 100]

let animation = CABasicAnimation(keyPath: "transform.scale.x")
animation.fromValue = 1
animation.toValue = 2
```

<br/>

## Example
```Swift
@objc func handleTapGesture(_ sender: UITapGestureRecognizer) {
   let sceneViewTappedOn = sender.view as! SCNView
   let touchCoordinates = sender.location(in: sceneViewTappedOn)
   let hitTest = sceneViewTappedOn.hitTest(touchCoordinates)

   if hitTest.isEmpty {
      print("didn't touch anything")
   } else {
      let result = hitTest.first!
      let node = result.node
      if node.animationKeys.isEmpty {
         self.animateNode(node: node)
      }
   }
}


func animateNode(node: SCNNode) {
   let spin = CABasicAnimation(keyPath: "position")
   spin.fromValue = node.presentation.position
   spin.toValue = SCNVector3(
      node.presentation.position.x - 0.2,
      node.presentation.position.y - 0.2,
      node.presentation.position.z - 0.2)
   spin.duration = 0.07
   spin.repeatCount = 5
   spin.autoreverses = true
   node.addAnimation(spin, forKey: "position")
}
```

[Apple Documents][apple]

[apple]: https://developer.apple.com/documentation/quartzcore/cabasicanimation
