# npmtest-airbnb-prop-types

#### basic test coverage for  [airbnb-prop-types (v2.5.3)](https://github.com/airbnb/prop-types#readme)  [![npm package](https://img.shields.io/npm/v/npmtest-airbnb-prop-types.svg?style=flat-square)](https://www.npmjs.org/package/npmtest-airbnb-prop-types) [![travis-ci.org build-status](https://api.travis-ci.org/npmtest/node-npmtest-airbnb-prop-types.svg)](https://travis-ci.org/npmtest/node-npmtest-airbnb-prop-types)

#### Custom React PropType validators that we use at Airbnb.

[![NPM](https://nodei.co/npm/airbnb-prop-types.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/airbnb-prop-types)

| git-branch : | [alpha](https://github.com/npmtest/node-npmtest-airbnb-prop-types/tree/alpha)|
|--:|:--|
| coverage : | [![istanbul-coverage](https://npmtest.github.io/node-npmtest-airbnb-prop-types/build/coverage.badge.svg)](https://npmtest.github.io/node-npmtest-airbnb-prop-types/build/coverage.html/index.html)|
| test-report : | [![test-report](https://npmtest.github.io/node-npmtest-airbnb-prop-types/build/test-report.badge.svg)](https://npmtest.github.io/node-npmtest-airbnb-prop-types/build/test-report.html)|
| build-artifacts : | [![build-artifacts](https://npmtest.github.io/node-npmtest-airbnb-prop-types/glyphicons_144_folder_open.png)](https://github.com/npmtest/node-npmtest-airbnb-prop-types/tree/gh-pages/build)|

- [https://npmtest.github.io/node-npmtest-airbnb-prop-types/build/coverage.html/index.html](https://npmtest.github.io/node-npmtest-airbnb-prop-types/build/coverage.html/index.html)

[![istanbul-coverage](https://npmtest.github.io/node-npmtest-airbnb-prop-types/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fcoverage.lib.html.png)](https://npmtest.github.io/node-npmtest-airbnb-prop-types/build/coverage.html/index.html)

- [https://npmtest.github.io/node-npmtest-airbnb-prop-types/build/test-report.html](https://npmtest.github.io/node-npmtest-airbnb-prop-types/build/test-report.html)

[![test-report](https://npmtest.github.io/node-npmtest-airbnb-prop-types/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Ftest-report.html.png)](https://npmtest.github.io/node-npmtest-airbnb-prop-types/build/test-report.html)

- [https://npmdoc.github.io/node-npmdoc-airbnb-prop-types/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-airbnb-prop-types/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-airbnb-prop-types/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-airbnb-prop-types/build/apidoc.html)

![npmPackageListing](https://npmtest.github.io/node-npmtest-airbnb-prop-types/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmtest.github.io/node-npmtest-airbnb-prop-types/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "name": "airbnb-prop-types",
    "version": "2.5.3",
    "description": "Custom React PropType validators that we use at Airbnb.",
    "main": "index.js",
    "dependencies": {
        "array.prototype.find": "^2.0.4",
        "has": "^1.0.1",
        "is-regex": "^1.0.4",
        "object.assign": "^4.0.4",
        "object.entries": "^1.0.4",
        "prop-types": "^15.5.4"
    },
    "devDependencies": {
        "babel-cli": "^6.24.1",
        "babel-plugin-istanbul": "^4.1.1",
        "babel-preset-airbnb": "^2.2.3",
        "babel-register": "^6.24.1",
        "chai": "^3.5.0",
        "eslint": "^3.19.0",
        "eslint-config-airbnb": "^14.1.0",
        "eslint-plugin-import": "^2.2.0",
        "eslint-plugin-jsx-a11y": "^4.0.0",
        "eslint-plugin-react": "^6.10.3",
        "mocha": "^3.2.0",
        "nyc": "^10.2.0",
        "object.values": "^1.0.4",
        "react": "^15.5.3",
        "rimraf": "^2.6.1",
        "safe-publish-latest": "^1.1.1"
    },
    "peerDependencies": {
        "react": "^0.14 || ^15.0.0"
    },
    "scripts": {
        "pretest": "npm run lint",
        "test": "npm run travis",
        "travis": "npm run build && npm run test:only",
        "test:only": "npm run mocha test",
        "test:all": "npm run test:only && npm run react:14 && npm run test:only && npm run react:15 && npm run test:only",
        "lint": "eslint --ext js,jsx src test",
        "prepublish": "npm run clean && npm run build && safe-publish-latest",
        "clean": "rimraf build",
        "build": "npm run clean && babel src --out-dir build --source-maps && npm run build:index",
        "prebuild:index": "cp index.js .index.js",
        "build:index": "babel index.js --out-file index.js --no-babelrc --source-maps",
        "postbuild:index": "mv .index.js index.js",
        "cover:clean": "rimraf coverage",
        "cover:run": "nyc --show-process-tree npm run --silent mocha test -- --reporter=dot",
        "precoverage": "NODE_ENV=test npm run build",
        "coverage": "npm run --quiet cover:clean && npm run --silent cover:run",
        "mocha": "mocha --recursive test/helpers/_failTestsOnErrors",
        "react:clean": "rimraf node_modules/react node_modules/react-dom node_modules/react-addons-test-utils",
        "react:14": "npm run react:clean && npm i react@0.14 react-dom@0.14 react-addons-test-utils@0.14",
        "react:15": "npm run react:clean && npm i react@15 react-dom@15 react-addons-test-utils@15"
    },
    "repository": {
        "type": "git",
        "url": "git+https://github.com/airbnb/prop-types.git"
    },
    "keywords": [
        "react",
        "propTypes",
        "airbnb",
        "prop",
        "types",
        "validator",
        "validation"
    ],
    "author": "Jordan Harband <ljharb@gmail.com>",
    "license": "MIT",
    "bugs": {
        "url": "https://github.com/airbnb/prop-types/issues"
    },
    "homepage": "https://github.com/airbnb/prop-types#readme"
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
