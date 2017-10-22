## 기초
* 너무 긴 이름, 아주 많은 항목
* 크로스 브라우징 (Mobile, IE)


## 공통
* 밸리데이션(중복/예약), 관계(상위/하위), 알림(혹은 컨펌)
* 낙관적 업데이트(Optimistic updates): 작업중일때(isSyncing) 다른 작업 제한
* 읽기
  - state: error > idle(=fetching) > 404 || data
  - 실시간 데이터베이스 (Firebase)


## Category
### 추가
* 밸리데이션: 중복이 있으면 차단(알림), 예약어인 경우 차단(알림) 혹은 변형

### 수정
* 밸리데이션: (추가와 같음)
* 관계: 상위/하위 관계에도 필요한지 점검(필요시 알림)

### 삭제
* 관계: 하위 관계의 항목들 모두 삭제(알림)


## Articles
### 추가
* 밸리데이션: 항목에 따른 밸리데이션 (length, exists, fetchingResult, ...)

### 수정
* 밸리데이션:
  - category: 존재하지 않으면 생성
  - deleted: 복원할 상위 항목이 존재하지 않으면 생성

### 삭제
* 컨펌


## ETC
* 샘플 임포트
* 스토리지 비우기
* 휴지통 비우기


## Auth
* Sign up, Sign in, Sign out
  - 새로고침 혹은 동기화
  - 상태에 따라 페이지 리다이렉트
  - 헤더 토글
* 로그인 전/후, 자신/타인의 계정 열람에 따른 기능 권한 제한
  - 이동간 이전의 스토어 상태 때문에 깜빡임이 생기지 않도록 UI 상태 및 Fetch 타이밍 고려


## Drag and drop
### Drag
* `canDrag: false`: 앱이 작업중이거나, 해당 컴포넌트가 작업중일때
* 시각적 인디케이팅: `canDrag`, `isDragging`

### Drop
* `canDrop: false`: 해당 컴포넌트가 원래 있던 컨테이너
* 시각적 인디케이팅: `canDrop && isOver`

### 예외
* inbox로는 이동 불가
* Trash로도 이동 가능
* Trash로부터 이동할 때 복원 등 별도의 액션 필요


## Form
* Error, submitting, submitSuceeded
* pristine, validation(client/server)
* AutoFocus, AutoComplete
* Submit 후 필요시 history.push()
