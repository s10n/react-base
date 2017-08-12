## Design
* Database structure
* Routes


## Init app
* Set title of project `public/index.html`
* Lint in editor `.eslintrc`
  ```json
  {
    "extends": "react-app"
  }
  ```
* Add essential packages
  - [Prettier](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md#formatting-code-automatically)
  ```bash
  yarn add --dev husky lint-staged prettier
  ```
* Style [reboot.css](https://github.com/s10n/reboot.css)

### Optional
```bash
yarn add react-router
yarn add react-helmet
yarn add --dev react-snapshot@next
```


## Development
* Unit test
* Action and Reducers
  - [Redux DevTools extension](http://extension.remotedev.io/)
* Components
  - [Storybook or Styleguidist](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md#developing-components-in-isolation)
    ```sh
    getstorybook
    ```


## Deployment
* [Sentry](https://sentry.io)
* [Google Analytics](https://www.google.com/analytics/)
* [Source map explorer](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md#analyzing-the-bundle-size)
  ```sh
  yarn add --dev source-map-explorer
  ```
  ```json
  "scripts": {
    "analyze": "source-map-explorer build/static/js/main.*"
  }
  ```
* [Firebase launch checklist](https://firebase.google.com/support/guides/launch-checklist)


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
