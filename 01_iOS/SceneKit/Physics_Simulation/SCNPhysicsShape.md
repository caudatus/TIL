# SCNPhysicsShape
An abstraction of a physics body’s solid volume for tuning collision detection.

SCNPhysicsBody를 구현한 물리적인 바디객체의 입체 부피의 충돌 감지를 조율하기 위한 추상클래스이다.

## Example
```Swift
let box = SCNNode(geometry: SCNBox(width: 0.1, height: 0.1, length: 0.1, chamferRadius: 0))
box.geometry?.firstMaterial?.diffuse.contents = UIColor.blue
box.position = currentPositionOfCamera

let body = SCNPhysicsBody(type: .dynamic, shape: SCNPhysicsShape(node: box, options: [SCNPhysicsShape.Option.keepAsCompound: true]))
box.physicsBody = body

self.sceneView.scene.rootNode.addChildNode(box)
```


[Apple Documents][apple]

[apple]: https://developer.apple.com/documentation/scenekit/scnphysicsshape
