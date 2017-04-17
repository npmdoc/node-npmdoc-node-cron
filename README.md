# api documentation for  [node-cron (v1.1.3)](http://merencia.com/node-cron/)  [![npm package](https://img.shields.io/npm/v/npmdoc-node-cron.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-node-cron) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-node-cron.svg)](https://travis-ci.org/npmdoc/node-npmdoc-node-cron)
#### A simple cron-like task scheduler for Node.js

[![NPM](https://nodei.co/npm/node-cron.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/node-cron)

- [https://npmdoc.github.io/node-npmdoc-node-cron/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-node-cron/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-node-cron/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-node-cron/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-node-cron/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-node-cron/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Lucas Merencia"
    },
    "bugs": {
        "url": "https://github.com/merencia/node-cron/issues"
    },
    "dependencies": {},
    "description": "A simple cron-like task scheduler for Node.js",
    "devDependencies": {
        "coveralls": "^2.11.6",
        "expect.js": "^0.3.1",
        "istanbul": "^0.4.2",
        "mocha": "^3.0.2",
        "sinon": "^1.17.3"
    },
    "directories": {},
    "dist": {
        "shasum": "f161c743812302d50f5251bd93ca57019a5298d2",
        "tarball": "https://registry.npmjs.org/node-cron/-/node-cron-1.1.3.tgz"
    },
    "gitHead": "a042f1209ebf99cf5e3a1783bb33e0e434f84cde",
    "homepage": "http://merencia.com/node-cron/",
    "keywords": [
        "cron",
        "scheduler",
        "schedule",
        "task",
        "job"
    ],
    "license": "ISC",
    "main": "src/node-cron.js",
    "maintainers": [
        {
            "name": "merencia"
        }
    ],
    "name": "node-cron",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git+https://github.com/merencia/node-cron.git"
    },
    "scripts": {
        "check": "npm run coverage && npm run coveralls",
        "coverage": "istanbul cover _mocha -- --recursive",
        "coveralls": "cat ./coverage/lcov.info | ./node_modules/coveralls/bin/coveralls.js",
        "test": "./node_modules/mocha/bin/mocha --recursive"
    },
    "version": "1.1.3"
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
