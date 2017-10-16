## 문서

### Jest
* [Mock Functions](https://facebook.github.io/jest/docs/en/mock-functions.html)
  - 목 함수는 함수의 실제 구현을 지우고, 함수로의 콜들을 캡쳐한다. (그리고 이 콜들안으로 파라피터를 전달한다)
* [Mock Functions API](https://facebook.github.io/jest/docs/en/mock-function-api.html)

### Enzyme
* [Shallow Rendering API](http://airbnb.io/enzyme/docs/api/shallow.html)
  - 단위로서 컴포넌트를 테스트
* [Full Rendering API (`mount(...)`)](http://airbnb.io/enzyme/docs/api/mount.html)
  - DOM API들과 상호작용해야하는 컴포넌트
  - 컴포넌트의 라이프사이클 (`componentDidMount`)


## 튜토리얼

### React
* [Testing React Apps](https://facebook.github.io/jest/docs/en/tutorial-react.html) \| Jest
* [React + TDD = 💖](https://medium.com/@admm/test-driven-development-in-react-is-easy-178c9c520f2f)
  - 리액트 컴포넌트 TDD 기초
  - `mockFn`, `mockClear`
* [How to Unit Test React Redux Components](http://ericnish.io/blog/how-to-unit-test-react-redux-components/)
  - 가장 깔끔한 방법은 state가 props로 전달된 순수한 컴포넌트를 테스트하는 것
  - props만이 유일한 디펜던시이며, 컴포넌트는 props만 읽는다.
  - Connected Component가 실제 애플리케이션에서 사용되겠지만, 베이스 컴포넌트를 테스트한다.
  - fake props를 mock한다.
* [Testing in React: Getting Off The Ground](https://medium.com/javascript-inside/testing-in-react-getting-off-the-ground-5f569f3088a)
  - input에 change를 시뮬레이트하고 함수가 호출되는지 여부 파악하는 테스트

### Redux
* [Unit Testing Redux Container Components - Part 1](http://www.wsbrunson.com/react/redux/test/2016/05/08/testing-redux-containers.html)
  - `<Provider>`
  - https://github.com/Gethyl/ReactReduxTestingUsingJestEnzyme/blob/master/__test__/Home.spec.js
  - https://medium.com/@gethylgeorge/testing-a-react-redux-app-using-jest-and-enzyme-b349324803a9#.6wposzhpp
* [Some Thoughts On Testing React/Redux Applications](https://medium.com/javascript-inside/some-thoughts-on-testing-react-redux-applications-8571fbc1b78f)
  - Jest, Enzyme
  - Async (Redux-thunk)
* [Testing React & Redux Applications](https://medium.com/caffeine-and-testing/testing-react-redux-applications-fee79ac0087f)
  - `import configureMockStore from 'redux-mock-store'`
