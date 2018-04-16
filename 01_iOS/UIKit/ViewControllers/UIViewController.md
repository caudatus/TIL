# UIViewController

## ViewController 특징
- child UIViewController
- UserInteraction
  - UIResponder를 상속받은 클래스로 이벤트 체인으로 부터 오는 이벤트를 처리한다. 모든 이벤트는 ViewController가 받아 해당 메소드와 델리게이트로 전달한다.
- Data Marshaling(중계자)
  - 자신이 관리하는 view들과 앱 내부의 데이터와의 중계자 역할을 한다.
- Resource Management
  - ViewController안의 모든 뷰와 오브젝트를 책임진다. 메모리 부족시 didReceiveMemoryWarning() 메소드가 자동을 불리며 사용하지 않는 객체와 다시 쉽게 만들수 있는 객체를 제거하여 메모리를 효율적으로 관리한다.

<br/>

## 생명주기
1. loadView()
2. viewDidLoad()
3. viewWillAppear(_ animated: Bool)
4. viewWillLayoutSubviews()
5. viewDidLayoutsubviews()
6. viewDidAppear(_ animated: Bool)
7. viewWillDisappear(_ animated: Bool)
8. viewDidDisappear(_ animated: Bool)
