# Usage

#### Install

Including peer dependencies.

```
yarn add -D eslint \
  prettier \
  @typescript-eslint/parser \
  @typescript-eslint/eslint-plugin \
  eslint-plugin-jest \
  eslint-plugin-prettier \
  eslint-plugin-react \
  eslint-plugin-react-hooks \
  eslint-plugin-simple-import-sort \
  eslint-plugin-import \
  @stoplight/eslint-config
```

#### Setup

Create a `.eslintrc.js` file in the root of the repository with contents:

```js
module.exports = {
  extends: ['@stoplight'],
};
```

Create a `.prettierrc.js` file in the root of the repository with contents:

```js
module.exports = {
  ...require('@stoplight/eslint-config/prettier.config'),
};
```

#### Typical Script Commands

```json
{
  "scripts": {
    "lint": "yarn prettier.check && eslint --ext .js,.jsx,.ts,.tsx .",
    "prettier.check": "prettier --ignore-path .eslintignore --check '**/*.{js,jsx,ts,tsx,md}'",
    "lint.fix": "prettier --ignore-path .eslintignore --write '**/*.{js,jsx,ts,tsx,md}'; eslint --ext .js,.jsx,.ts,.tsx . --fix"
  }
}
```

#### Typical `.eslintignore` File

```bash
node_modules
dist
build
coverage
.eslintrc.js
.yalc
.yarn
.cache
gen
```
