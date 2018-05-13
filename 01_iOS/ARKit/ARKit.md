# ARKit
Integrate iOS device camera and motion features to produce augmented reality experiences in your app or game.

앱이나 게임 내에서 AR(augmented reality)경험을 할 수 있도록 디바이스 카메라와 motion features를 통합한다.

## important
ARKit requires an iOS device with an A9 or later processor.
To make your app available only on devices supporting ARKit, use the arkit key in the UIRequiredDeviceCapabilities section of your app's Info.plist. If augmented reality is a secondary feature of your app, use the isSupported property to determine whether the current device supports the session configuration you want to use.

ARKit은 A9 및 이 후 프로세서를 장착한 디바이스가 필요하다. 앱이 ARKit을 지원하는 디바이스에서만 동작하도록 하려면 Info.plist의 UIRequiredDeviceCapabilities 섹션에 arkit key를 이용하여야 한다.
증강현실 기능이 앱의 부수적인 기능이라면 isSupported 프로퍼티를 사용하여 디바이스가 세션 구성을 지원하는지 확인하면 된다.

## Note
All AR configurations use one of the device's built-in cameras. Your app's Info.plist must include user-facing text for the NSCameraUsageDescription key so that the user can grant your app permission to access the camera. (If you create a new ARKit app using the Xcode template, a description is provided for you.)

모든 AR 구성은 디바이스의 카메라 중 하나를 사용한다. 따라서 앱의  Info.plist에는 NSCameraUsageDescription 키에 대한 사용자 지향 안내 문구가 있어야 사용자가 앱에 카메라 사용 권한을 부여할 수 있다. Xcode 템플릿을 사용하여 ARKit 앱을 제작하는 경우 위의 키 및 안내문구는 자동으로 제공된다.


[Apple Documents][apple]

[apple]: https://developer.apple.com/documentation/arkit
