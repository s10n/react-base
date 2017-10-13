# Deploy app

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
