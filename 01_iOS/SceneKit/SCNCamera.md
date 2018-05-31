# SCNCamera
A set of camera attributes that can be attached to a node to provide a point of view for displaying the scene.

scene을 표시하기위한 시점을 제공하기 위해 노드에 첨부 할 수있는 일련의 카메라 속성.

## Overview
To display a scene, you must designate a node whose camera property contains a camera object as the point of view.

The [SCNNode][1] object containing a camera defines a point of view—that is, the position and orientation of the camera. A camera’s direction of view is always along the negative z-axis of the node’s local coordinate system. To point the camera at different parts of your scene, use the [position][2], [rotation][3], or [transform][4] property of the node containing it. (Alternatively, to ensure that a camera always points at a particular element of your scene even when that element moves, attach a [SCNLookAtConstraint][5] object to the node containing the camera.)

An SCNCamera object itself defines the shape and, in part, the appearance of the rendered scene as seen from its point of view. By default, a camera defines a perspective projection, whose field of view (FOV) and near and far visibility limits you control using the properties listed in [Adjusting Camera Perspective][6] and illustrated below.

scene을 표시하려면 카메라 속성이 포함 된 노드를 시점(point of view)으로 지정해야 합니다.

카메라가 포함 된 [SCNNode][1] 객체는 시점(즉, 카메라의 위치와 방향)을 정의합니다. 카메라 view의 방향은 항상 노드의 로컬 좌표계의 음의 z축을 따릅니다. scene의 다른 부분을 가리키도록 카메라를 포함하는 노드의 [position][2](위치), [rotation][3](회전) 또는 [transform][4](변형) 속성을 사용할수 있습니다. (또는 카메라가 해당 요소가 움직이는 경우에도 scene의 특정 요소를 항상 가리키는지 확인하려면 [SCNLookAtConstraint][5] 객체를 카메라가 포함 된 노드에 연결하십시오.)

SCNCamera 객체 자체는 형태와 그 시점에서 바라본 렌더링 된 scene의 모양을 정의합니다. 기본적으로 카메라는 원근 투영법을 정의하며, 이 투시도는 [카메라 시점 조정][6] 및 아래 그림에 나열된 속성을 사용하여 FOV(Field Of View) 및 원근의 가시도 제한을 제어합니다.

<img src="/image/SCNCamera.png">


[Apple Documents][apple]




[1]: ./SCNNode.md
[2]: https://developer.apple.com/documentation/scenekit/scnnode/1408026-position
[3]: https://developer.apple.com/documentation/scenekit/scnnode/1408034-rotation
[4]: https://developer.apple.com/documentation/scenekit/scnnode/1407964-transform
[5]: ./Constraints/SCNLookAtConstraint.md
[6]: https://developer.apple.com/documentation/scenekit/scncamera#1655112
[apple]: https://developer.apple.com/documentation/scenekit/scncamera?changes=_4
