# UIDevice
A representation of the current device.

현재 디바이스를 나타내는 객체 입니다.

## Overview
Use a UIDevice object to get information about the device such as assigned name, device model, and operating-system name and version. You also use the UIDevice instance to detect changes in the device’s characteristics, such as physical orientation. You get the current orientation using the orientation property or receive change notifications by registering for the UIDeviceOrientationDidChange notification. Before using either of these techniques to get orientation data, you must enable data delivery using the beginGeneratingDeviceOrientationNotifications() method. When you no longer need to track the device orientation, call the endGeneratingDeviceOrientationNotifications() method to disable the delivery of notifications.

Similarly, you can use the UIDevice instance to obtain information and notifications about changes to the battery’s charge state (described by the batteryState property) and charge level (described by the batteryLevel property). The UIDevice instance also provides access to the proximity sensor state (described by the proximityState property). The proximity sensor detects whether the user is holding the device close to their face. Enable battery monitoring or proximity sensing only when you need it.

You can also use the playInputClick() instance method to play keyboard input clicks in custom input and keyboard accessory views.

할당 된 이름, 장치 모델, 운영 체제 이름 및 버전과 같은 장치 정보를 얻으려면 UIDevice 객체를 사용하십시오. 또한 UIDevice 인스턴스를 사용하여 물리적 방향과 같은 장치의 변화를 감지합니다. [orientation][1] property를 사용하여 현재 방향값을 가져 오거나 [UIDeviceOrientationDidChange][2] notification을 등록하여 변경 알림을 받습니다. 이러한 기술 중 하나를 사용하여 방향 데이터를 가져 오기 전에 [beginGeneratingDeviceOrientationNotifications()][3] 메소드를 사용하여 데이터 전달을 활성화 해야합니다. 디바이스 방향을 더 이상 추적 할 필요가 없으면 [endGeneratingDeviceOrientationNotifications()][4] 메소드를 호출하여 알림 설정을 비활성화하십시오.

마찬가지로 UIDevice 인스턴스를 사용하여 배터리의 충전 상태 ([batteryState][5] property로 설명) 및 충전 레벨 ([batteryLevel][6] property로 설명)에 대한 변경 사항에 대한 정보와 알림을 얻을 수 있습니다. UIDevice 인스턴스는 근접 센서 상태 ([proximityState][7] property로 설명)에 대한 액세스도 제공합니다. 근접 센서는 사용자가 얼굴 가까이에서 디바이스를 잡고 있는지 여부를 감지합니다. 필요한 경우에만 배터리 모니터링 또는 근접 감지를 활성화하십시오.

[playInputClick()][8] 인스턴스 메서드를 사용하여 사용자 정의 입력 및 키보드 accessory views에서 키보드 입력 클릭을 재생할 수도 있습니다.


[Apple Documents][apple]






[1]: https://developer.apple.com/documentation/uikit/uidevice/1620053-orientation
[2]: https://developer.apple.com/documentation/foundation/nsnotification.name/1620025-uideviceorientationdidchange
[3]: https://developer.apple.com/documentation/uikit/uidevice/1620041-begingeneratingdeviceorientation
[4]: https://developer.apple.com/documentation/uikit/uidevice/1620033-endgeneratingdeviceorientationno
[5]: https://developer.apple.com/documentation/uikit/uidevice/1620051-batterystate
[6]: https://developer.apple.com/documentation/uikit/uidevice/1620042-batterylevel
[7]: https://developer.apple.com/documentation/uikit/uidevice/1620058-proximitystate
[8]: https://developer.apple.com/documentation/uikit/uidevice/1620050-playinputclick
[apple]: https://developer.apple.com/documentation/uikit/uidevice
