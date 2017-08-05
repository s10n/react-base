## Init app
* Set title of project
* Lint in editor
  ```json
  {
    "extends": "react-app"
  }
  ```
* Add essential packages
  ```sh
  yarn add --dev husky lint-staged prettier
  ```
* Design databases structure
* Design routes
* Style reboot.css

## Packages
* Storybook or Styleguidist
  ```sh
  getstorybook
  ```
* Source map explorer
  ```sh
  yarn add --dev source-map-explorer
  ```
  ```json
  "scripts": {
    "analyze": "source-map-explorer build/static/js/main.*"
  }
  ```

## Advanced
* Unit test
* Code Splitting
