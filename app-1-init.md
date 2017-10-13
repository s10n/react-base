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
* [Reboot css](https://github.com/s10n/reboot.css)
* [Add optional packages](http://nomad.works/study/front-end/links-library)
