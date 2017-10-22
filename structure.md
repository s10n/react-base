# 겪어온 시행착오들

* 삭제했다는 표시로 `deleted: true`를 사용할 때의 주의사항
  - Category에 Articles 목록을 props로써 전달할 때 `deleted: true`를 미리 필터링할 것인가?
  - 만약 해당 Category를 삭제할 때 속한 Articles의 카테고리 필드를 제거하는 작업이 있다면, `deleted: true`인 Articles은 이 작업의 대상에서 제외될 것이다.

* 낙관적 업데이트를 할 때의 주의사항
  - 어떤 Article의 필드가 예를들어 { name, slug }뿐이었다고 가정한다.
  - 만약 원래 없었던 `deleted: true`라는 필드를 추가한다면, 낙관적 업데이트가 실패했을 때 `deleted: false`로 되돌릴 방법을 마련해야한다.

* Redux로 상태를 관리하는 애플리케이션에서 여러 개의 모달이 필요할 때의 주의사항
  - store에 방대한 virtual dom 전체를 저장하지 않는다.
  - 데이터만 전달한다. 데이터를 받아 렌더하는 것은 컴포넌트의 역할이다.

* 퍼포먼스
  - 반복적으로 출력할 컴포넌트가 있다면, `PureComponent` 혹은 `componentShouldUpdate`로 re-rendering을 제한해야 한다.

* 마운트 여부 판단
  - 어떤 컴포넌트의 마운트 여부는 상위 컴퍼넌트에서 결정해줘야 한다.
  - 그렇지 않으면 `componentWillMount`에 필요한 데이터가 아직 없을때 mount되거나, 불필요한 연산을 미리 해버리게 될 여지가 있다.

* 상호 참조가 초래하는 순서 꼬임
  - 아래처럼 두 개의 모듈이 서로를 import하면, 빌드 순서가 꼬여서 한 쪽은 의도한대로 동작하지 않을 수 있다.
  ```js
  // env.js
  import { tier } from './project'

  // project.js
  import { build } from './env'
  ```
