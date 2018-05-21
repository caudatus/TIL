# ARConfiguration
The abstract base class for AR session configurations.

AR session 구성에 있어 기본이 되는 추상클래스

## Overview
To run an AR session, create an instance of the concrete ARConfiguration subclass that provides the kind of augmented reality experience you want to use in your app or game. Then, set up the configuration object's properties and pass the configuration to your session's run(_:options:) method. ARKit includes the following concrete configuration classes:

- [ARWorldTrackingConfiguration][arworld]
  - Provides high-quality AR experiences that use the rear-facing camera precisely track a device's position and orientation and allow plane detection and hit testing.
- AROrientationTrackingConfiguration
  - Provides basic AR experiences that use the rear-facing camera and track only a device's orientation.
- ARFaceTrackingConfiguration
  - Provides AR experiences that use the front-facing camera and track the movement and expressions of the user's face.


AR session을 실행시키기 위해서는 사용하길 원하는 AR환경에 맞는 ARConfiguration 서브클래스를 생성해야 한다. 그런다음 configuration 객체의 프로퍼티로 설정을 하고 session의 run(_:options:)메서드에 이 객체를 전달하여야 한다. ARKit은 다음의 configuration 클래스를 가지고 있다.

- [ARWorldTrackingConfiguration][arworld]
- AROrientationTrackingConfiguration
- ARFaceTrackingConfiguration

[Apple Documents][apple]


[arworld]: 01_iOS/ARKit/ARWorldTrackingConfiguration.md
[apple]: https://developer.apple.com/documentation/arkit/arconfiguration
