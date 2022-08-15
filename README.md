# 팀 프로젝트가 나에게 남긴 것

팀 프로젝트를 처음 시작할 때는 레벨1, 레벨2 때처럼 '그냥 ~' 하고 별 생각 없이 그냥 시작한 것 같다. 이런저런 일들도 많았고
가장 크게 느껴지는 부분을 크게 두 가지 파트로 나눠서 적어보려고 한다.

## 협업 vs 개인 미션

협업은 지금까지 진행했던 개인 미션과는 아주 달랐다. 어찌 됐든 누군가와 `같이`하는 과정이기 때문에 고려해야 할 상황들이 정말 많았다. 감정적인 부분, 작업 방식이나 스타일에 관한 부분, 작업 시간에 관한 부분, 바라보고 있는 목표가 `텍스트`는 같았지만, `실제 생각`은 달랐던 부분, 소통에 관한 부분까지 가장 큰 부분이었다고 생각하는 것은 두 가지인데 아래에서 살펴보자.

### 바라보고 있는 목표가 `텍스트`는 같았지만 `실제 생각`은 달랐다.

"우리 리팩토링은 나중에 하고 기능부터 하자" 이 말을 다르게 해석해서 생긴 문제가 있었다. 나한테는 리팩토링은 `코드를 컨벤션에 맞게 고치고, 구조를 유지보수하기 원활하게 바꾸는 것`이었는데 상대방은 기능 추가를 하면서 어차피 건드려야 하는 파일은 코드를 컨벤션에 맞게 고쳐야 한다고 생각했다.
나는 새로 작업하는 코드라면 컨벤션에 맞도록 작성해야 하지만, 이전에 작성된 코드를 수정하게 된다고 전체 코드가 컨벤션에 맞는지 체크할 수는 없다고 생각했다. 일단 기능을 먼저 추가하기로 했으니까. 그래서 같이 liveshare를 켜놓고 작업하다가 충돌이 일어났다.
"왜 px로 되어있는 거 rem으로 안 고쳐?", "왜 color 테마에서 안 들고 오는데 안 고쳐?" 이런 이야기가 오고 가다 서로 이해를 못 하고 감정만 상하다 결국 그날의 마무리 미팅 때 터졌었다.
이런 부분은 소통의 부재의 문제라고 생각했다. 한 단어가 여러 의미로 해석되지 않도록 이제는 한 번 더 깊게 되묻거나 최대한 해석의 여지가 없는 단어를 선택해서 소통하려고 노력하게 되었다.

### 작업 방식과 스타일

꽤 고생했던 부분이다. 혼자 짜는 코드야 컨벤션이고 뭐고 나만 코드 일관성을 알아서 정해서 지키면 된다. 그러다 다른 방식이 좋다고 생각하면 맘대로 수정하고 할 수 있는 거다. 하지만 누군가와 코드를 공유하는 상황에서는 그렇지 않다는 것을 처음에는 피부에 와닿지 않아서 중간중간 문제가 많이 생겼다. 한 번 회의해서 정해진 내용은 이제 나중에 이전에 작업한 내용들이 바뀌어야 하는 합당한 이유 들고 가서 설득이나 이의제기해서 받아들여지기 전까지는 `무조건` 지켜야 하는 규칙이 되는 거니까.
그래서 협업 초반에는 일단 잘 모르겠으면 "일단 그렇게 해보자~" 라고 했지만, 문제가 한 번 터지고 저걸 깨달은 지금은 굉장히 세부적으로 따져본다. 코드 전반인 마크업 컨벤션, 상수화 컨벤션부터 세부적일 수도 있는 화살표 함수의 단축 구문은 어떤 상황에서만 사용해야 하는지까지. 모두 팀 노션의 프론트엔드 회의록의 코딩 컨벤션에 추가해서 지킨다.
이러한 부분들이 협업하며 많이 배운 부분이라 생각한다.

## Git

git은 언제나 나에게 마음의 짐이었다. 레벨1, 2 진행하면서도 미션 저장조에서 fork 해와서 commit, push, pr만 남기면 됐었기 때문에 거의 봇처럼 깃을 사용하고 있었다.
그러나 협업할 때 git는 생각보다 신경 써야 할 것이 많았다. 깃 브랜칭 따로 연습해보려고 [Learn Git Branching](https://learngitbranching.js.org/?locale=ko)로 레벨 다 깼는데도 그것보다 실제로 협업하면서 문제들을 많이 일으키면서 git을 많이 배우고 익숙해진 것 같다.

### 폴더이름, 파일이름 -> 대, 소문자만 변경

첫 번째로 생긴 문제는 이거였다. 스프린트 1 도중 main에 머지된 파일이 좀비 파일처럼 절대 안 날아가는 이상한 상황이 발생했는데, 나중에 알고 보니 git이 파일, 폴더이름의 대, 소문자만 바뀌면 인식하지 못해서 로컬 정보가 제대로 반영이 되지 않으면서 생긴 문제였다.
카멜 케이스로 작성해야 하는 파일명이 파스칼케이스로 작성되어있는 것을 고친 것뿐이었는데 그 당시에는 커밋도 안 되고, 삭제도 안 되는 좀비파일이 main에 머지되어버려서 대참사가 났었다. 스프린트 3 데모데이 날에 똑같은 문제가 발생했는데 팀 노선의 `트러블슈팅`에 적어놓은 해결법 덕분에 쉽게 해결할 수 있었다.

### 올바른 시점에서 분기 생성하기

스프린트 2가 끝나고 develop 브랜치가 생기고 일어난 일이었는데, 스프린트 3 시작할 때 생성된 develop에서 분기 브랜치를 생성해서 작업을 하고, pr를 develop 브랜치에 보내는 식으로 작업을 해야 했는데 main 브랜치나 스프린트 2 마지막에 작업하던 main과 동일한 로컬 브랜치에서 분기 브랜치를 생성해서 작업을 시작하면서 또 대참사가 일어났다.
pr을 보낼 때마다 스프린트 3가 시작되고 분기를 친 시점부터의 모든 커밋이 포함되어서 자꾸 작업은 나 혼자 한 건데 관련 없는 사람들이 작업기여자로 추가가 되고, 마지막으로 데모데이를 위해 develop에서 main으로 머지할 때도 conflict가 엄청났었다. 그 경험으로 git의 전반적인 이해가 전에 비해 매우 높아졌다는 생각이 들었다.
