# Core Motion
Process accelerometer, gyroscope, pedometer, and environment-related events.

물리가속도계, 자이로스코프, 계보기(걸음의 수를 재는 기구), 이벤트 처리와 관련된 디바이스의 프로세스를 처리

<br/>

## 중요
iOS 10.0 이후 버전을 지원하는 앱들에서 사용하기 위해서는 반드시 Info.plist 파일에 [NSMotionUsageDescription][nsmotionusage] Key를 포함시켜야 한다. 그렇지 않으면 앱은 crash가 발생한다.

## First Steps
- class CMMotionManager
  - The object for starting and managing motion services.
  - 디바이스 모션 처리를 시작하고 관리하는 객체

```Swift
let motionManager = CMMotionManager()
```


[Apple Documents][apple]


[apple]: https://developer.apple.com/documentation/coremotion
[nsmotionusage]: https://developer.apple.com/library/content/documentation/General/Reference/InfoPlistKeyReference/Articles/CocoaKeys.html#//apple_ref/doc/uid/TP40009251-SW21
