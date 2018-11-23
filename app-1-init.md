# Init app

* Init files
  - Delete unnecessary files and lines
  - Set title of project `public/index.html`

* Add essential packages
  ```sh
  yarn add node-sass
  yarn add --dev husky lint-staged prettier
  ```
  ```json
  "husky": {
    "hooks": {
      "pre-commit": "lint-staged"
    }
  },
  "lint-staged": {
    "src/**/*.{js,jsx,json,scss}": [
      "prettier --single-quote --no-semi --write",
      "git add"
    ]
  }
  ```
  ```sh
  prettier --single-quote --no-semi --write "src/**/*.{js,jsx,json,scss}"
  ```

* Finish
  ```sh
  yarn start
  git commit -m "Init app"
  ```  

## Next
* Set favicon
  - [Favicon Generator](http://realfavicongenerator.net/)
* [Add optional packages](http://nomad.works/study/front-end/links-library)
* [Reboot css](https://github.com/s10n/reboot.css)

---
## Version 1.x
* Lint in editor `.eslintrc`
  ```json
  { "extends": "react-app" }
  ```

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
