# ARFrame
A video image, with position-tracking information, captured as part of an AR session.

AR 세션의 일부로 캡처 된 위치 추적 정보가 있는 비디오 이미지.

## Overview
A running AR session continuously captures video frames from the device camera. For each frame, ARKit analyzes the image together with data from the device's motion sensing hardware to estimate the device's real-world position. ARKit delivers this tracking information and imaging parameters in the form of an ARFrame object.

실행중인 AR 세션은 지속적으로 디바이스 카메라에서 비디오 프레임을 캡처합니다. 각 프레임마다 ARKit은 장치의 실제 위치를 예측하기 위해 장치의 동작 감지 하드웨어의 데이터와 함께 이미지를 분석합니다. ARKit은 이 추적 정보와 이미징 매개 변수를 ARFrame 객체 형태로 전달합니다.


[Apple Documents][apple]


[apple]: https://developer.apple.com/documentation/arkit/arframe
