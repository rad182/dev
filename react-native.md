## Create and Initialize Project
```
$ react-native init <projectName>
$ cd <projectName>
```
## Setup eslint and prettier
```
$ yarn add -D eslint eslint-config-airbnb eslint-plugin-import eslint-plugin-react eslint-plugin-react-native eslint-plugin-jsx-a11y babel-eslint eslint-config-prettier eslint-plugin-prettier prettier
```

copy .eslintrc and .eslintignore

## Setup Husky
```
$ yarn add -D husky lint-staged
```
add in package.json
```
"lint-staged": {
  "*.js": [
    "eslint --fix",
    "git add"
  ]
},
"husky": {
  "hooks": {
    "pre-commit": "lint-staged"
  }
}
```
add in package.json under `scripts` (adjust paths if needed)
```
"eslint": "eslint app/**",
"eslint-check": "eslint --print-config .eslintrc | eslint-config-prettier-check",
"prettier": "prettier --write 'app/**/*.js'"
```

be sure to follow folder structure

optional vscode workspace settings
```json
{
  // Format a file on save. A formatter must be available, the file must not be auto-saved, and editor must not be shutting down.
  "editor.formatOnSave": true,
  // Enable/disable default JavaScript formatter (For Prettier)
  "javascript.format.enable": false,
  // Use 'prettier-eslint' instead of 'prettier'. Other settings will only be fallbacks in case they could not be inferred from eslint rules.
  "prettier.eslintIntegration": true,
  "eslint.autoFixOnSave": true,
  "prettier.singleQuote": true
}
```
