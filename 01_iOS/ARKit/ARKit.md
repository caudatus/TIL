# ARKit
Integrate iOS device camera and motion features to produce augmented reality experiences in your app or game.

앱이나 게임 내에서 AR(augmented reality)경험을 할 수 있도록 디바이스 카메라와 motion features를 통합한다.

## Overview
Augmented reality (AR) describes user experiences that add 2D or 3D elements to the live view from a device's camera in a way that makes those elements appear to inhabit the real world. ARKit combines device motion tracking, camera scene capture, advanced scene processing, and display conveniences to simplify the task of building an AR experience. You can use these technologies to create many kinds of AR experiences using either the back camera or front camera of an iOS device.

Augmented reality (AR)은 기기의 카메라에서 라이브 뷰에 2D 또는 3D 요소를 추가하여 사용자가 실제 세상에 존재하는 것처럼 보이게 만드는 사용자 경험을 나타냅니다. ARKit은 장치 모션 추적, 카메라 장면 캡처, 고급 장면 처리 및 편의성 표시 기능을 결합하여 AR 경험 구축 작업을 단순화합니다. 이러한 기술을 사용하여 iOS 기기의 후면 카메라 또는 전면 카메라를 사용하여 다양한 종류의 AR 경험을 만들 수 있습니다.



## important
ARKit requires an iOS device with an A9 or later processor.
To make your app available only on devices supporting ARKit, use the arkit key in the UIRequiredDeviceCapabilities section of your app's Info.plist. If augmented reality is a secondary feature of your app, use the isSupported property to determine whether the current device supports the session configuration you want to use.

ARKit은 A9 및 이 후 프로세서를 장착한 디바이스가 필요하다. 앱이 ARKit을 지원하는 디바이스에서만 동작하도록 하려면 Info.plist의 UIRequiredDeviceCapabilities 섹션에 arkit key를 이용하여야 한다.
증강현실 기능이 앱의 부수적인 기능이라면 isSupported 프로퍼티를 사용하여 디바이스가 세션 구성을 지원하는지 확인하면 된다.

## Note
All AR configurations use one of the device's built-in cameras. Your app's Info.plist must include user-facing text for the NSCameraUsageDescription key so that the user can grant your app permission to access the camera. (If you create a new ARKit app using the Xcode template, a description is provided for you.)

You can display a 3D object in the user's real-world environment without building a custom AR experience. In iOS 12, the system provides an AR view for 3D objects when you use [QLPreviewController][1] with USDZ files in an app, or use Safari or WebKit with USDZ files in web content.

모든 AR 구성은 디바이스의 카메라 중 하나를 사용한다. 따라서 앱의  Info.plist에는 NSCameraUsageDescription 키에 대한 사용자 지향 안내 문구가 있어야 사용자가 앱에 카메라 사용 권한을 부여할 수 있다. Xcode 템플릿을 사용하여 ARKit 앱을 제작하는 경우 위의 키 및 안내문구는 자동으로 제공된다.

사용자 정의 AR 환경을 구축하지 않고도 사용자의 실제 환경에서 3D 객체를 표시 할 수 있습니다. iOS 12에서는 앱에서 USDZ 파일과 함께 [QLPreviewController][1]를 사용하거나 웹 콘텐츠에서 USDZ 파일과 함께 Safari 또는 WebKit을 사용할 때 시스템에서 3D 개체에 대한 AR보기를 제공합니다.

[Apple Documents][apple]


[1]: /01_iOS/QuickLook/QLPreviewController.md
[apple]: https://developer.apple.com/documentation/arkit
