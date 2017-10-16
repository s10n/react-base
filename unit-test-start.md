# React 유닛 테스트

## 필요한 패키지

### 설치
```sh
yarn add --dev prop-types enzyme enzyme-adapter-react-16 react-test-renderer jest-enzyme
```

### 설정: `src/setupTests.js`
```js
import { configure } from 'enzyme'
import Adapter from 'enzyme-adapter-react-16'
import 'jest-enzyme'

configure({ adapter: new Adapter() })
```

### 참고
* [Running Test](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md#running-tests) \| create-react-app
* [Installation](http://airbnb.io/enzyme/docs/installation/) \| Enzyme


## 테스트 API
* [Jest](https://facebook.github.io/jest/docs/en/expect.html): `expect()`
* [Enzyme](http://airbnb.io/enzyme/docs/api/shallow.html): `shallow()`
* [jest-enzyme](https://github.com/blainekasten/enzyme-matchers): `expect(wrapper.contains(welcome)).toEqual(true)`을 간단히 `expect(wrapper).toContainReact(welcome)`처럼 쓸 수 있게 해준다.


## 테스트 예시

### React - 컴포넌트
```jsx
import React from 'react'
import { shallow } from 'enzyme'
import App from './App'

describe('App', () => {
  let props, wrapper

  beforeEach(() => {
    props = {}
    wrapper = shallow(<App {...props} />)
  })

  it('renders itself', () => {
    expect(wrapper.exists()).toBeTruthy()
  })
})
```

### Redux - 비동기 액션
* [Async Action Creators](http://redux.js.org/docs/recipes/WritingTests.html#async-action-creators) \| Redux
  ```sh
  yarn add --dev redux-mock-store nock
  ```

  - `redux-mock-store`: mock the store
  - `nock`: mock the HTTP request

