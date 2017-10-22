# Init app

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
  +     "prettier --single-quote --no-semi --write",
  +     "git add"
  +   ]
  + }
  ```
* [Add optional packages](http://nomad.works/study/front-end/links-library)

## Stylesheets
* SCSS
  ```sh
  yarn add --dev node-sass-chokidar npm-run-all
  ```

  - `packages.json`
  ```diff
  "scripts": {
  +   "start": "npm-run-all -p start-css start-js",
  +   "start-js": "react-scripts start",
  +   "start-css": "npm run build-css && node-sass-chokidar --include-path ./src --include-path ./node_modules src/ -o src/ --watch --recursive",
  +   "build": "npm-run-all build-css build-js",
  +   "build-js": "react-scripts build",
  +   "build-css": "node-sass-chokidar --include-path ./src --include-path ./node_modules src/ -o src/",
  ```

  - `.gititnore`
  ```diff
  + src/**/*.css
  ```

* [Reboot css](https://github.com/s10n/reboot.css)
