Provide haptic feedback in response to specific types of events.

특정 타입의 이벤트에 반응하는 햅틱 피드백을 제공한다.

# UIFeedbackGenerator
The abstract superclass for all feedback generators.

모든 feedback generators의 추상 슈퍼클래스 이다.

## Overview
Do not subclass or create instances of this class yourself. Instead, instantiate one of the provided concrete subclasses:
[UIImpactFeedbackGenerator][impact] Use impact feedback generators to indicate that an impact has occurred. For example, you might trigger impact feedback when a user interface object collides with something or snaps into place.
[UISelectionFeedbackGenerator][select] Use selection feedback generators to indicate a change in selection.
[UINotificationFeedbackGenerator][noti] Use notification feedback generators to indicate successes, failures, and warnings.

이 클래스의 인스턴스를 직접 서브 클래싱하거나 생성하지 마시오.
대신, 아래 제공된 구체적인 하위 클래스 중 하나를 인스턴스화 하시오.
[UIImpactFeedbackGenerator][impact]를 사용하여 영향이 발생했음을 나타낸다. 예를 들어, 사용자 인터페이스 객체가 무언가와 충돌하거나 제자리로 들어갈 때 햅틱 피드백을 트리거 할 수 있습니다.
[UISelectionFeedbackGenerator][select]를 사용하여 선택, 변경을 햅틱 피드백을 제공할 수 있다.
[UINotificationFeedbackGenerator][noti]를 사용하 성공, 실패, 경고에 햅틱 피드백을 제공할 수 있다.

<br/>

## Using Feedback Generators
To use a feedback generator, the following are required:
1. Instantiating the Generator
2. Preparing the Generator (optional)
3. Triggering Feedback
4. Releasing the Generator (optional).

```Swift
var feedbackGenerator : UISelectionFeedbackGenerator? = nil
@IBAction func gestureHandler(_ sender: UIPanGestureRecognizer) {

    switch(sender.state) {
    case .began:

        // Instantiate a new generator.
        feedbackGenerator = UISelectionFeedbackGenerator()

        // Prepare the generator when the gesture begins.
        feedbackGenerator?.prepare()

    case .changed:

        // Check to see if the selection has changed...
        if  myCustomHasSelectionChangedMethod(translationPoint: sender.translation(in: view)) {

            // Trigger selection feedback.
            feedbackGenerator?.selectionChanged()

            // Keep the generator in a prepared state.
            feedbackGenerator?.prepare()
        }

    case .cancelled, .ended, .failed:

        // Release the current generator.
        feedbackGenerator = nil

    default:
        // Do Nothing.
        break
    }}
```

</br>

## Triggering Feedback
Each feedback generator subclass has a unique triggering method.
To trigger feedback, call the appropriate method:
`impactOccurred()`

`selectionChanged()`

`notificationOccurred(_:)`

<br/>

[Apple Documents][apple]


[impact]: https://developer.apple.com/documentation/uikit/uiimpactfeedbackgenerator
[select]: https://developer.apple.com/documentation/uikit/uiselectionfeedbackgenerator
[noti]: https://developer.apple.com/documentation/uikit/uinotificationfeedbackgenerator
[apple]: https://developer.apple.com/documentation/uikit/uifeedbackgenerator
