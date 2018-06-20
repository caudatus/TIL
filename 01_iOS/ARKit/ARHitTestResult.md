# ARHitTestResult
Information about a real-world surface found by examining a point in the device camera view of an AR session.

AR 세션의 device camera view에서 한 지점을 test하여 real-world surface에 대한 정보를 찾을 수 있습니다.

## Overview
If you display an AR experience using SceneKit or SpriteKit, you can use one of the following methods to search the camera image for real-world content at a point specified in view coordinates:

- [ARSCNView hitTest(_:types:)][1]
- [ARSKView hitTest(_:types:)][2]

Otherwise, you can search the camera image for real-world content using the [ARFrame hitTest (_:types:)][3] method. Because a frame is independent of a view, for this method you pass a point specified in normalized image coordinates (where (0,0) is the top left corner of the image and (1,1) is the lower right).

All these methods return an array of ARHitTestResult objects describing the content found. The number and order of results in the array depends on the search types you specify and the order you specify them in. For example, consider the code below:

```Swift
let results = view.hitTest(point, [.existingPlaneUsingGeometry, .estimatedHorizontalPlane])
```

This hitTest(_:types:) call searches first for plane anchors already present in the session (according to the session configuration's [planeDetection][4] settings); returning any such results (in order of distance from the camera) as the first elements in the array. This call also (due to the [estimatedHorizontalPlane][5] request) attempts to determine whether the hit test ray intersects any horizontal surface not already found by plane detection, and returns that result (if any) as the last element in the array.

SceneKit 또는 SpriteKit을 사용하여 AR 경험을 표시하는 경우 다음 methods 중 하나를 사용하여 뷰 좌표에 지정된 지점에서 실제 이미지가 있는지 카메라 이미지를 검색 할 수 있습니다.

- [ARSCNView hitTest(_:types:)][1]
- [ARSKView hitTest(_:types:)][2]

그렇지 않으면 [ARFrame hitTest (_:types:)][3] 메소드를 사용하여 카메라 이미지에서 실제 컨텐츠를 검색 할 수 있습니다. 프레임은 뷰와는 관계가 없기 때문에,이 메소드에서는, 정규화 된 이미지 좌표로 지정된 포인트를 건네줍니다 (여기서 (0,0)은 이미지의 좌상 구석, (1,1)은 우하 구석입니다).

이러한 모든 메소드는 발견 된 내용을 설명하는 ARHitTestResult 객체의 배열을 반환합니다. 배열의 갯수와 순서는 지정한 검색 유형과 사용자가 지정한 순서에 따라 달라집니다. 예를 들어 다음 코드를 고려하십시오.

```Swift
let results = view.hitTest(point, [.existingPlaneUsingGeometry, .estimatedHorizontalPlane])
```

이 hitTest (_:types:) 호출은 먼저 세션에 이미있는 plane anchors를 검색합니다 (세션 구성의 [planeDetection][4] 설정에 따라 다름). (카메라로부터의 거리의 순서로) 그러한 결과를 배열의 첫 번째 요소로 반환합니다. 이 호출은 또한 [estimatedHorizontalPlane][5] 요청으로 인해 히트 테스트 광선이 평면 검출에 의해 아직 발견되지 않은 수평 표면과 교차하는지 여부를 결정하고 배열의 마지막 요소로 해당 결과를 반환합니다.

[Apple Documents][apple]


[1]: https://developer.apple.com/documentation/arkit/arscnview/2875544-hittest
[2]: https://developer.apple.com/documentation/arkit/arskview/2875733-hittest
[3]: https://developer.apple.com/documentation/arkit/arframe/2875718-hittest
[4]: https://developer.apple.com/documentation/arkit/arworldtrackingconfiguration/2923548-planedetection
[5]: https://developer.apple.com/documentation/arkit/arhittestresult/resulttype/2887460-estimatedhorizontalplane
[apple]: https://developer.apple.com/documentation/arkit/arhittestresult
