# ARSKView
A view for displaying AR experiences that augment the camera view with 2D SpriteKit content.

2D SpriteKit content가 표시되는 카메라 뷰의 품질을 높여 AR 경험을 표시하는 뷰

<br/>

## Overview
Use the ARSKView class to create augmented reality experiences that position 2D elements in 3D space within a device camera view of the real world. When you run the view's provided ARSession object:

- The view automatically renders the live video feed from the device camera as the scene background.
 - When you implement ARSKViewDelegate methods to associate SpriteKit content with real-world positions, the view automatically scales and rotates those SpriteKit nodes so that they appear to track the real world seen by the camera.

AR 환경을 2D요소를 디바이스 카메라로 읽어드린 3차원 실제 공간에 배치할때
ARSKView 클래스를 사용한다. ARSession 객체가 있는 뷰가 실행될때:
-  scene 백그라운드에서 디바이스 카메라를 사용하여 라이브 비디오 피드를 자동으로 렌더링 한다.
- 실제 3차원 공간에 SpriteKit 컨텐츠를 표시하기위해 ARSKViewDelegate 메소드를 구현할때, 뷰는 자동으로 SpriteKit 노드의 크기와 회전을 조절한다.


[Apple Documents][apple]

[apple]: https://developer.apple.com/documentation/arkit/arskview
