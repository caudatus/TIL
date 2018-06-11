# SCNMorpher
An object that manages smooth transitions between a node's base geometry and one or more target geometries.

노드의 기본 지오메트리와 하나 이상의 타겟 지오메트리 간의 부드러운 전환을 관리하는 객체입니다.

## Overview
Figure 1
Morphing between a sphere geometry and two target geometries

sphere 지오메트리와 두 개의 타겟 지오메트리 간의 모핑
<img src="/image/SCNMorpher.png">

You control these transitions by associating an SCNMorpher object with a node using its [morpher][1] property. The morpher maintains an array of target geometries and a set of weights associated with each. When all weights are zero, the surface takes the form of the base geometry (from the node’s [geometry][2] property). When you use the [setWeight(_:forTargetAt:)][3] method to increase a weight to 1.0, the surface takes the form of the geometry at the corresponding index in the morpher’s [targets][4] array. If you use a variety of weight values for several targets, the surface takes a form that proportionally interpolates between the target geometries.

You can also animate weights implicitly or explicitly using keypath animations. For example, the following code creates a morph animation that transitions one target weight back and forth repeatedly:

SCNMorpher 객체를 [morpher][1] 속성을 사용하는 노드와 연결하여 이러한 전환을 제어합니다. morpher는 타겟 지오메트리의 배열과 각 지오메트리와 연관된 weights 세트를 유지 관리합니다. 모든 weights가 0이면, surface는 기본 geometry의 양식 (노드의 [geometry][2] 속성에서)을 취합니다. [setWeight(_:forTargetAt:)][3] 메소드를 사용하여 weight를 1.0으로 늘리면, morpher의 [타겟][4] 배열에 있는 해당 index에서 지오메트리의 형태를 취합니다. 여러 target에 대해 다양한 weight를 사용하면 표면은 타겟 Geometry간에 비례 적으로 보정되는 양식을 취합니다.

keypath 애니메이션을 사용하여 weights를 암시적 또는 명시적으로 애니메이션으로 만들 수도 있습니다. 예를 들어 다음 코드는 하나의 타겟 weight를 앞뒤로 반복 전환하는 모프 애니메이션을 만듭니다.

```Swift
CABasicAnimation *animation = [CABasicAnimation animationWithKeyPath:@"morpher.weights[0]"];
animation.fromValue = @0.0;
animation.toValue = @1.0;
animation.autoreverses = YES;
animation.repeatCount = INFINITY;
animation.duration = 5;
[node addAnimation:animation forKey:nil];
```

A morpher and its target geometries may be loaded from a scene file or created programmatically. The base geometry and all target geometries must be topologically identical—that is, they must contain the same number and structural arrangement of vertices.

Morpher와 그 타겟 도형은 씬 파일로부터 로드되거나 프로그래밍 방식으로 생성 될 수 있습니다. 기본 지오메트리와 모든 타겟 지오메트리는 위상적으로 동일해야합니다. 즉, 동일한 수와 정점의 구조적 배열을 포함해야합니다.

[Apple Documents][apple]



[1]: https://developer.apple.com/documentation/scenekit/scnnode/1408022-morpher
[2]: https://developer.apple.com/documentation/scenekit/scnnode/1407966-geometry
[3]: https://developer.apple.com/documentation/scenekit/scnmorpher/1522886-setweight
[4]: https://developer.apple.com/documentation/scenekit/scnmorpher/1523572-targets
[apple]: https://developer.apple.com/documentation/scenekit/scnmorpher
