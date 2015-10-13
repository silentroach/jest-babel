# Simple Babel preprocessor for Jest

## Usage

Install the package:

    $ npm install jest-babel --save-dev

Add preprocessor to your `package.json`:

```json
{
  "scripts": {
    "test": "jest"
  },
  "jest": {
    "scriptPreprocessor": "<rootDir>/node_modules/jest-babel",
    "preprocessorIgnorePatterns": ["/node_modules/"],
    "testFileExtensions": ["es6", "js"],
    "moduleFileExtensions": ["js", "json", "es6"]
  }
}
```

If you want to transpile your dependencies, you can skip the key `preprocessorIgnorePatterns`.

## Extending default config

By default babel will transform your code with this config:

```json
{
  "stage": 2,
  "retainLines": true,
  "auxiliaryCommentBefore": "istanbul ignore next"
}
```

You can override or extend it with `jest-babel` section in your `package.json`:

```json
{
  "jest-babel": {
    "stage": 1,
    "extensions": ["es6", "customext"]
  }
}
```
