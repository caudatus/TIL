# Constraints
Automatically adjust the position or orientation of a node based on specified rules.

지정된 규칙을 기반으로 노드의 위치 또는 방향을 자동으로 조정합니다.

## Overview
By modifying the results of animation, physics, and other scene graph changes, constraints make it easier manage dynamic behaviors and relationships between elements of your scene.

For example, when developing a game, you might want a camera node to always point at the player character, even as that character moves around the scene. Instead of directly reorienting the camera node each time you move the character, you can add a look-at constraint to the camera node to make SceneKit reorient the camera automatically.

애니메이션, 물리 및 기타 씬 그래프 변경 결과를 수정하면 동적 비헤이비어와 scene 요소 간 관계를 쉽게 관리 할 수 ​​있습니다.

예를 들어, 게임을 개발할 때, 캐릭터가 장면을 돌아 다니더라도 카메라 노드가 항상 플레이어 캐릭터를 가리 키도록 할 수 있습니다. 캐릭터를 움직일 때마다 카메라 노드의 방향을 직접 바꾸는 대신 카메라 노드에 Look-At Constraint를 추가하여 SceneKit에서 자동으로 카메라의 방향을 재조정 할 수 있습니다.

[Apple Documents][apple]

[apple]: https://developer.apple.com/documentation/scenekit/constraints?changes=_4
