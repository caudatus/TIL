# App Life Cycle

iOS에서 앱은 3가지 실행모드와 5가지의 상태로 구분이 가능하며 항상 하나의 상태를 가지고 있다.

- Not Running
  - 실행되고 있지 않는 모드와 상태를 의미
- Foreground
  - Active
  - Inactive
- Background
  - Runnig
  - Suspend

<br/>

  - Not Running >> Active
    - 앱을 터치해서 실행이 되는 상태입니다.
  - Active >> Inactive >> Running
    - 앱을 활성화 상태에서 비활성화 상태로 만든 뒤, 백그라운드에서도 계속 실행중인 상태입니다.
  - Active >> Inactive >> Suspend
    - 앱을 활성화 상태에서 비활성화 상태로 만든 뒤, 백그라운드에서도 정지되어 있는 상태입니다.
  - Running >> Active
    - 백그라운드에서 실행 중인 앱이 다시 포어그라운드에서 활성화되는 상태입니다.


  ## Reference
  [Apple](https://developer.apple.com/library/content/documentation/iPhone/Conceptual/iPhoneOSProgrammingGuide/TheAppLifeCycle/TheAppLifeCycle.html#//apple_ref/doc/uid/TP40007072-CH2-SW1)
