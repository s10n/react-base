## Design
* Database structure
* Routes
  - Domain
  - 404


## Init app
* Set title of project `public/index.html`
* Set favicon
  - [Favicon Generator](http://realfavicongenerator.net/)
* Lint in editor `.eslintrc`
  ```json
  { "extends": "react-app" }
  ```
* Add essential packages
  - [Prettier](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md#formatting-code-automatically)
  ```bash
  yarn add --dev husky lint-staged prettier
  ```
  ```diff
  + "precommit": "lint-staged"
  ```
  ```diff
  + "lint-staged": {
  +   "src/**/*.{js,jsx,json,css}": [
  +     "prettier --single-quote --no-semi --print-width 100 --write",
  +     "git add"
  +   ]
  + }
  ```
* [Reboot css](https://github.com/s10n/reboot.css)

### Optional
* Packages
  ```bash
  yarn add redux react-redux keymirror
  yarn add react-router-dom
  yarn add axios redux-thunk
  yarn add firebase
  yarn add react-helmet
  yarn add --dev react-snapshot@next
  ```
  - [All About React Router 4](https://css-tricks.com/react-router-4/)


## Development
* Unit test
  - [Running Test](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md#running-tests)
* Action and Reducers
  - [Redux DevTools extension](http://extension.remotedev.io/)
  - [Improve your development workflow with Redux DevTools Extension](https://medium.com/@zalmoxis/improve-your-development-workflow-with-redux-devtools-extension-f0379227ff83)
  - [Using Redux DevTools in production](https://medium.com/@zalmoxis/using-redux-devtools-in-production-4c5b56c5600f)
* Components
  - [Storybook or Styleguidist](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md#developing-components-in-isolation)
    ```sh
    getstorybook
    ```


## Deployment
* Domain
* [Progressive Web App](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md#making-a-progressive-web-app)
* [Firebase launch checklist](https://firebase.google.com/support/guides/launch-checklist)
* [HTTP Referrer](https://console.developers.google.com/apis/credentials)
* [Sentry](https://sentry.io)
* [PageSpeed](https://developers.google.com/speed/pagespeed/)
* [Source map explorer](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md#analyzing-the-bundle-size)
  ```sh
  yarn add --dev source-map-explorer
  ```
  ```json
  "scripts": {
    "analyze": "source-map-explorer build/static/js/main.*"
  }
  ```
* [Google Analytics](https://www.google.com/analytics/)
* [Structured Data Testing Tool](https://search.google.com/structured-data/testing-tool)


## Collaboration
* README.md
  - How to build


## Advanced
* [Code Splitting](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md#code-splitting)


## Sentry configurations
* [Sentry Documentation](https://docs.sentry.io/)
  - [Release](https://docs.sentry.io/learn/releases/)
  - [Context](https://docs.sentry.io/learn/context/)
* [Javascript](https://docs.sentry.io/clients/javascript/)
  - [Whitelist urls](https://docs.sentry.io/clients/javascript/config/)
  - [Passing additional data](https://docs.sentry.io/clients/javascript/usage/#passing-additional-data)
  - [Source maps](https://docs.sentry.io/clients/javascript/sourcemaps/#making-source-maps-available-to-sentry)
* [Integrations](https://docs.sentry.io/integrations/)
  - [Github](https://docs.sentry.io/integrations/github/)
  - Slack
  - [Jira](https://docs.sentry.io/integrations/jira/)
