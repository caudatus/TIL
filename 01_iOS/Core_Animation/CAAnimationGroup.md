# CAAnimationGroup
An object that allows multiple animations to be grouped and run concurrently.

여러 애니메이션을 그룹화하여 동시에 실행할 수있게 해주는 객체입니다.

## Overview
The grouped animations run in the time space specified by the CAAnimationGroup instance.

The duration of the grouped animations are not scaled to the duration of their CAAnimationGroup. Instead, the animations are clipped to the duration of the animation group. For example, a 10 second animation grouped within an animation group with a duration of 5 seconds displays only the first 5 seconds of the animation.

Listing 1 shows how you can create a grouped animation containing opacity and scale animations to fade out a layer while expanding it. The animation starts with an opacity of 1 and a scale of 1 on all axes. As the animation's scale increases to (3, 3, 3), the opacity drops to 0 and the animated layer vanishes.

Listing 1. Creating an animation group
```Swift
let fadeOut = CABasicAnimation(keyPath: "opacity")
fadeOut.fromValue = 1
fadeOut.toValue = 0
fadeOut.duration = 1

let expandScale = CABasicAnimation()
expandScale.keyPath = "transform"
expandScale.valueFunction = CAValueFunction(name: kCAValueFunctionScale)
expandScale.fromValue = [1, 1, 1]
expandScale.toValue = [3, 3, 3]

let fadeAndScale = CAAnimationGroup()
fadeAndScale.animations = [fadeOut, expandScale]
fadeAndScale.duration = 1
```


그룹화 된 애니메이션은 CAAnimationGroup 인스턴스에 지정된 시간 공간에서 실행됩니다.

그룹화 된 애니메이션의 지속 시간은 해당 CAAnimationGroup의 지속 시간으로 조정되지 않습니다. 대신, 애니메이션은 애니메이션 그룹의 지속 시간으로 잘립니다. 예를 들어, 애니메이션 그룹 내에서 5 초의 기간으로 그룹화 된 10 초 애니메이션은 애니메이션의 처음 5 초만 표시합니다.

Listing 1은 불투명도와 스케일 애니메이션이 포함 된 그룹화 된 애니메이션을 생성하여 레이어를 확장하면서 페이드 아웃하는 방법을 보여줍니다. 애니메이션은 모든 축에서 1의 불투명도와 1의 축척으로 시작합니다. 애니메이션의 배율이 (3, 3, 3)으로 증가함에 따라 불투명도가 0으로 떨어지고 애니메이션 레이어가 사라집니다.

Listing 1. Creating an animation group
```Swift
let fadeOut = CABasicAnimation(keyPath: "opacity")
fadeOut.fromValue = 1
fadeOut.toValue = 0
fadeOut.duration = 1

let expandScale = CABasicAnimation()
expandScale.keyPath = "transform"
expandScale.valueFunction = CAValueFunction(name: kCAValueFunctionScale)
expandScale.fromValue = [1, 1, 1]
expandScale.toValue = [3, 3, 3]

let fadeAndScale = CAAnimationGroup()
fadeAndScale.animations = [fadeOut, expandScale]
fadeAndScale.duration = 1
```

## Important
The [delegate][1] and [isRemovedOnCompletion][2] properties of animations in the [animations][3] array are currently ignored. The CAAnimationGroup delegate does receive these messages.

[애니메이션][3] 배열의 애니메이션의 [delegate][1] 및 [isRemovedOnCompletion][2] 속성은 현재 무시됩니다. CAAnimationGroup delegate는 이러한 메시지를받습니다.




[Apple Documents][apple]

[1]: https://developer.apple.com/documentation/quartzcore/caanimation/1412490-delegate
[2]: https://developer.apple.com/documentation/quartzcore/caanimation/1412458-isremovedoncompletion
[3]: https://developer.apple.com/documentation/quartzcore/caanimationgroup/1412516-animations
[apple]: https://developer.apple.com/documentation/quartzcore/caanimationgroup
