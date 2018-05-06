# SCNShape
A geometry based on a two-dimensional path,
optionally extruded to create a three-dimensional object.

2차원 경로의 기하학 도형, 추가적으로 압출성형의 형태로 3차원 도형으로 만들수 있다.

```Swift
//ARKit 사용 중에
let node = SCNNode()
let path = UIBezierPath()
path.move(to: CGPoint(x: 0, y: 0))
path.addLine(to: CGPoint(x:0, y: 0.2))
path.addLine(to: CGPoint(x: 0.2, y:0.3))
path.addLine(to: CGPoint(x: 0.4, y: 0.2))
path.addLine(to: CGPoint(x: 0.4, y: 0))

let shape = SCNShape(path: path, extrusionDepth: 0.2)
node.geometry = shape

let x = randomNubers(firstNum: -0.3, secondNum: 0.3)
let y = randomNubers(firstNum: -0.3, secondNum: 0.3)
let z = randomNubers(firstNum: -0.3, secondNum: 0.3)
node.position = SCNVector3(x, y, z)

sceneView.scene.rootNode.addChildNode(node)

func randomNubers(firstNum: CGFloat, secondNum: CGFloat) -> CGFloat {
   return CGFloat(arc4random()) / CGFloat(UINT32_MAX) * abs(firstNum - secondNum) + min(firstNum, secondNum)
}
```

[Apple Documents][apple]


[apple]: https://developer.apple.com/documentation/scenekit/scnshape
