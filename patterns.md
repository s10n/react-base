## React Documentations

* [State and Lifecycle](https://facebook.github.io/react/docs/state-and-lifecycle.html)
  - State 갱신은 비동기적일 수 있다.
  ```js
  this.setState((prevState, props) => ({
    counter: prevState.counter + props.increment
  }))
  ```
* [Forms](https://facebook.github.io/react/docs/forms.html)
  - [Handling Multiple Inputs](https://facebook.github.io/react/docs/forms.html#handling-multiple-inputs)
  ```js
  handleInputChange(event) {
    const target = event.target
    const value = target.type === 'checkbox' ? target.checked : target.value
    const name = target.name

    this.setState({ [name]: value })
  }
  ```
* [Lifting State Up](https://facebook.github.io/react/docs/lifting-state-up.html)
  - 종종 여러 구성 요소가 동일한 변경 데이터를 반영해야한다. 가장 가까운 공통 조상까지 공유 상태를 들어올리는 것이 좋다.
  - [Temperature Calculator](http://codepen.io/valscion/pen/jBNjja?editors=0010)
* [Composition vs Inheritance](https://facebook.github.io/react/docs/composition-vs-inheritance.html)
* [JSX In Depth](https://facebook.github.io/react/docs/jsx-in-depth.html)
  - [Render a different component based on a prop](https://facebook.github.io/react/docs/jsx-in-depth.html#choosing-the-type-at-runtime)
  ```jsx
  import React from 'react';
  import { PhotoStory, VideoStory } from './stories';

  const components = {
    photo: PhotoStory,
    video: VideoStory
  };

  function Story(props) {
    // Wrong! JSX type can't be an expression.
    return <components[props.storyType] story={props.story} />;
  }
  ```


## React

* [10 React mini-patterns](https://hackernoon.com/10-react-mini-patterns-c1da92f068c5)

### HOC
* [PublicRoute, PrivateRoute](https://github.com/tylermcginnis/react-router-firebase-auth/blob/master/src/components/index.js) by partner of ReactTraining

### Middleware
* 역할: action과 reducer 사이에서의 처리
* 예시
  - rexux-logger
  - redux-thunk: 비동기 fetch action의 response 처리
  - 에러 핸들링: 어떤 API로부터 받은 프로퍼티의 이름과 내 앱이 사용 중인 것과 매치하지 않을 때


## Redux
* [Presentational and Container Components](https://medium.com/@dan_abramov/smart-and-dumb-components-7ca2f9a7c7d0)


## CMS

* Store
```js
const byId = (state = {}, action) => { ... }
const idsByFilter = (state = {}, action) => { ... }
```

* Delete
```js
_.omit(object, [paths]) // Object (단, _.pick보다 느리다.)
_.without(array, [values]) // Array
```

* Filter
```js
let items = this.state.items

if (this.state.filter) {
  items = items.filter(item =>
    item.name.toLowerCase().includes(this.state.filter.toLowerCase())
  )
}
```

* Sort
```js
data = data.slice().sort((a, b) => a.name > b.name)
```

* Toggle
```js
handleToggle() {
  if (!this.state.isEdit) {
    this.setState({
      name: this.props.contact.name,
      phone: this.props.contact.phone
    })
  } else {
    this.handleEdit()
  }

  this.setState({
    isEdit: !this.state.isEdit
  })
}
```

* Submit
```js
onFormSubmit(event) {
  event.preventDefault()
  // Do something...
}
```

### Packages
* [uuid](https://github.com/kelektiv/node-uuid)
* [Reselect](https://github.com/reactjs/reselect)
* [Normalizr](https://github.com/paularmstrong/normalizr)
* [Redux Bug Reporter](http://dtschust.github.io/redux-bug-reporter/)


## Utils

### Debounce function
```jsx
videoSearch(term) {
  // Search videos from API
}

render() {
  const videoSearch = _.debounce(term => this.videoSearch(term), 300)
  return <SearchBar onSearchTermChange={videoSearch} />
}
```
* [Debouncing and Throttling Explained Through Examples](https://css-tricks.com/debouncing-throttling-explained-examples/)


## API

### Google Map
```html
<script src="https://maps.googleapis.com/maps/api/js"></script>
```
```jsx
class GoogleMap extends Component {
  componentDidMount() {
    new google.maps.Map(this.refs.map, {
      zoom: 12, center: { lat: this.props.lat, lng: this.props.lon }
    })
  }

  render() {
    return <div ref="map" />
  }
}
```

### Fake REST API
* [JSONPlaceholder](https://jsonplaceholder.typicode.com)
