# Style guide


## Environments
* [Create React App](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md)
* Yarn
  - `yarn outdated`


## Conventions
1. [Create React App](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md#supported-language-features-and-polyfills)
  - ES6
  - Async/await
  - Object Rest/Spread Properties
  - Class Fields and Static Properties
  - [Component](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md#importing-a-component)
2. Prettier `--no-semi --single-quote`
3. [Airbnb React/JSX Style Guide](https://github.com/airbnb/javascript/tree/master/react)
  - [Naming](https://github.com/airbnb/javascript/tree/master/react#naming): `.jsx`
  - [Ordering](https://github.com/airbnb/javascript/tree/master/react#ordering): +style, +functions
  - [Props](https://github.com/airbnb/javascript/tree/master/react#props): Always define explicit defaultProps for all non-required props.

4. [Airbnb's Style Guide](https://github.com/airbnb/javascript)
  - [Object Shorthand](https://github.com/airbnb/javascript#es6-object-concise)
  - [Arrow Functions](https://github.com/airbnb/javascript#arrows--implicit-return)


### ES6
* Functional programming: Pure, Immutable

### React
* CSS in JS
* [Performance](https://reactjs.org/docs/optimizing-performance.html#profiling-components-with-the-chrome-performance-tab)
  - Binding function
  - Reselect

### Structure
* Folders: actions/reducers/store/ducks, components/**, pages, utils, styles, images
* Files
* Naming functions: verbNoun, CRUD


## Contribution
* [Git-flow](http://nvie.com/posts/a-successful-git-branching-model/)
* [Commit Message Guidelines](https://github.com/angular/angular/blob/master/CONTRIBUTING.md#-commit-message-guidelines)
  - 50/72
* [Semantic versioning](http://semver.org/)
* Issue tracker
* [Code Review Etiquette](https://css-tricks.com/code-review-etiquette/)


## Documentation
* README.md
  - How to build
* Comments
  - [The Art of Comments](https://css-tricks.com/the-art-of-comments/)


## More references
* [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript)
* [nomad.works/study](http://nomad.works/study/)
