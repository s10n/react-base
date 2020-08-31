# Init app

* Init files
  - Delete unnecessary files and lines
  - Set title of project `public/index.html`

* Add essential packages
  ```json
  "husky": {
    "hooks": {
      "pre-commit": "lint-staged"
    }
  },
  "lint-staged": {
    "src/**/*.{js,jsx,ts,tsx,json,css,scss,md}": [
      "prettier --single-quote --no-semi --write"
    ]
  }
  ```
  ```sh
  yarn add node-sass;
  yarn add husky lint-staged prettier;
  prettier --no-semi --write "src/**/*.{js,jsx,ts,tsx,json,css,scss,md}"
  ```

* Finish
  ```sh
  echo "SASS_PATH=node_modules:src" >> .env
  echo "BROWSER=none" >> .env.development
  git commit -m "Init app";
  yarn start
  ```

## PWA
```html
<meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=no" />
<link rel="icon" href="%PUBLIC_URL%/favicon.png" />
<link rel="apple-touch-icon" href="%PUBLIC_URL%/logo192.png" />
<link rel="manifest" href="%PUBLIC_URL%/manifest.json" />
```
```json
{
  "display": "standalone"
}
```

* Set favicon
  - [Favicon Generator](http://realfavicongenerator.net/)

## Next
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
