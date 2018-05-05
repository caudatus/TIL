# UIBezierPath
A path that consists of straight and curved line segments that you can render in your custom views.
custom views 에서 직선과 곡선의 요소로 구성된 경로를 만들수 있는 객체

```Swift
//집모양 3D 경로
let path = UIBezierPath()
path.move(to: CGPoint(x: 0, y: 0))
path.addLine(to: CGPoint(x:0, y: 0.2))
path.addLine(to: CGPoint(x: 0.2, y:0.3))
path.addLine(to: CGPoint(x: 0.4, y: 0.2))
path.addLine(to: CGPoint(x: 0.4, y: 0))

let shape = SCNShape(path: path, extrusionDepth: 0.2)
```

[Apple Documents][apple]

[apple]: https://developer.apple.com/documentation/uikit/uibezierpath
