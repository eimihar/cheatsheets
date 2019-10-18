# Package.json cheatsheet

Credit : https://flaviocopes.com/package-json/#name
```json
{
  "name": "test-project",
  "description": "A package to work with strings",
  "author": {
      "name": "Flavio Copes",
      "email": "flavio@flaviocopes.com",
      "url": "https://flaviocopes.com"
    },
  "contributors": [
      "Flavio Copes <flavio@flaviocopes.com> (https://flaviocopes.com)"
    ],
  "bugs": "https://github.com/flaviocopes/package/issues",
  "homepage": "https://flaviocopes.com/package",
  "version": "1.0.0",
  "license": "MIT",
  "keywords": [
    "email",
    "machine learning",
    "ai"
  ],
  "repository": {
    "type": "git",
    "url": "https://github.com/flaviocopes/testing.git"
  },
  "main": "src/main.js",
  "private": true,
  "scripts": {
    "dev": "webpack-dev-server --inline --progress --config build/webpack.dev.conf.js",
    "start": "npm run dev",
    "unit": "jest --config test/unit/jest.conf.js --coverage",
    "test": "npm run unit",
    "lint": "eslint --ext .js,.vue src test/unit",
    "build": "node build/build.js"
  },
  "engines": {
    "node": ">= 6.0.0",
    "npm": ">= 3.0.0",
    "yarn": "^0.13.0"
  },
  "browserslist": [
    "> 1%",
    "last 2 versions",
    "not ie <= 8"
  ]
}
```