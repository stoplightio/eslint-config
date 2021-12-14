# Usage

#### Install

Including peer dependencies.

```
yarn add -D @typescript-eslint/eslint-plugin \
  @typescript-eslint/parser \
  eslint \
  eslint-plugin-import \
  eslint-plugin-jest \
  eslint-plugin-prettier \
  eslint-plugin-react \
  eslint-plugin-react-hooks \
  eslint-plugin-simple-import-sort \
  prettier
```

Add `@stoplight/eslint-config`:

```
yarn add -D @stoplight/eslint-config
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
