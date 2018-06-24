# SCNPhysicsBody
The physics simulation attributes attached to a scene graph node.

scene의 graph node(child node)에 부여하는 물리적인 시뮬레이션 속성

## Overview
When SceneKit prepares to render a new frame, it performs physics calculations on physics bodies attached to nodes in the scene. These calculations include gravity, friction, and collisions with other bodies. You can also apply your own forces and impulses to a body. After SceneKit completes these calculations, it updates the positions and orientations of the node objects before rendering the frame.

SceneKit은 새로운 프레임을 렌더링 할 준비를 할 때, scene의 노드에 부착 된 물리 구조물에 대한 물리 계산을 수행합니다. 이 계산에는 중력, 마찰 및 다른 신체와의 충돌이 포함됩니다. 당신은 또한 자신의 힘과 충동을 몸에 적용 할 수 있습니다. SceneKit이이 계산을 완료하면 프레임을 렌더링하기 전에 노드 객체의 위치와 방향을 업데이트합니다.



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
