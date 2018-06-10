# SCNTransaction
A mechanism for creating implicit animations and combining scene graph changes into atomic updates.

암시적 애니메이션을 만들고 scene graph 변경을 최소 업데이트로 결합하는 메커니즘입니다.

<br/>

## Overview
You use SCNTransaction class methods to control the animation that results from changing animatable properties in the scene graph and to combine sets of changes into nested transactions.

SCNTransaction 클래스 메서드를 사용하여 scene graph의 애니메이션 가능한 속성을 변경하여 생기는 애니메이션을 제어하고 변경 집합을 중첩된 트랜잭션으로 결합합니다.

<br/>

## Adding Animation with Automatic Transaction
SceneKit creates a transaction automatically whenever you modify the objects in a scene graph. This transaction groups any additional changes you make from the same thread during the current iteration of that thread’s run loop. When the run loop next iterates, SceneKit automatically commits the transaction, atomically applying all changes made during the transaction to the presentation scene graph (that is, the, version of the scene graph currently being displayed).

Because an automatic transaction has a default duration of zero, any changes it contains appear instantly when SceneKit automatically commits the transaction. By using the setAnimationDuration() method to change the duration, you implicitly animate all changes made to animatable properties during the transaction. You can use implicit animation to add animation to a scene quickly and easily. For example, the code in Listing 1 fades out and moves one node, fades in another, moves and zooms the point of view camera, and focuses a spotlight, all in a single one-second animation.

SceneKit은 scene graph에서 객체를 수정할 때마다 자동으로 트랜잭션을 생성합니다. 이 트랜잭션은 해당 스레드의 실행 루프가 반복되는 동안 동일한 스레드에서 변경 한 사항을 그룹화합니다. 실행 루프가 다음에 반복 될 때, SceneKit은 트랜잭션 중에 자동으로 트랜잭션을 커밋하여 트랜잭션 중에 발생하는 모든 변경 사항을 프레젠테이션 scene graph (즉, 현재 표시된 scene graph의 버전)에 적용합니다.

자동 트랜잭션은 기본 지속 시간이 0이므로, SceneKit이 자동으로 트랜잭션을 커밋 할 때 포함된 모든 변경 사항이 즉시 나타납니다. `setAnimationDuration()` 메소드를 사용하여 지속 기간을 변경하면 트랜잭션 중에 애니메이션 가능 특성에 대한 모든 변경 사항에 내재적으로 애니메이션을 적용 할 수 있습니다. 암시적 애니메이션을 사용하여 장면을 빠르고 쉽게 추가 할 수 있습니다. 예를 들어, 아래의 코드는 하나의 노드를 페이드 아웃하고 이동시키고, 다른 노드에서 페이드 인하고, 시점 카메라를 이동 및 확대하고, 스포트라이트에 포커스를 맞추는 모든 것을 하나의 애니메이션으로 나타낸다.

```Swift
[SCNTransaction setAnimationDuration:1.0];
_textNode.position = SCNVector3Make(0.0, -10.0, 0.0);
_textNode.opacity = 0.0;
_heroNode.opacity = 1.0;
view.pointOfView = _heroCamera;
_heroCamera.camera.yFov = 20.0;
_lightNode.light.spotInnerAngle = 30.0;
```

<br/>

## Creating Advanced Animations with Custom Transactions
You can also use SCNTransaction class methods to create and manage a hierarchy of your own transactions. By nesting custom transactions, you can group sets of scene graph changes, applying different animation parameters to each group. Use the begin() method to create a custom transaction, nested within the current transaction if one exists. Use the commit() method to end a transaction, applying all scene graph changes made within.

또한 SCNTransaction 클래스 메소드를 사용하여 자신의 트랜잭션 계층을 작성하고 관리 할 수 ​​있습니다. 사용자 정의 트랜잭션을 중첩하여 scene graph 변경 세트를 그룹화하고 각 그룹에 다른 애니메이션 매개 변수를 적용 할 수 있습니다. `begin()` 메서드를 사용하여 현재 트랜잭션 내에 중첩 된 사용자 정의 트랜잭션을 만듭니다. `commit()` 메서드를 사용하여 트랜잭션을 종료하고 내부에서 수행된 모든 scene graph 변경 사항을 적용합니다.

[Apple Documents][apple]


[apple]: https://developer.apple.com/documentation/scenekit/scntransaction
