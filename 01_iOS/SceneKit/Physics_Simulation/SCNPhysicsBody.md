# SCNPhysicsBody
The physics simulation attributes attached to a scene graph node.

scene의 graph node(child node)에 부여하는 물리적인 시뮬레이션 속성

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

[apple]: https://developer.apple.com/documentation/scenekit/scnphysicsbody
