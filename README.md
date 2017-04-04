# api documentation for  [node-cron (v1.1.3)](http://merencia.com/node-cron/)  [![npm package](https://img.shields.io/npm/v/npmdoc-node-cron.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-node-cron) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-node-cron.svg)](https://travis-ci.org/npmdoc/node-npmdoc-node-cron)
#### A simple cron-like task scheduler for Node.js

[![NPM](https://nodei.co/npm/node-cron.png?downloads=true)](https://www.npmjs.com/package/node-cron)

[![apidoc](https://npmdoc.github.io/node-npmdoc-node-cron/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-node-cron_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-node-cron/build/apidoc.html)

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
            "name": "merencia",
            "email": "lucas.merencia@gmail.com"
        }
    ],
    "name": "node-cron",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
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



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module node-cron](#apidoc.module.node-cron)
1.  [function <span class="apidocSignatureSpan">node-cron.</span>schedule (expression, func, immediateStart)](#apidoc.element.node-cron.schedule)
1.  [function <span class="apidocSignatureSpan">node-cron.</span>scheduled_task (task, immediateStart)](#apidoc.element.node-cron.scheduled_task)
1.  [function <span class="apidocSignatureSpan">node-cron.</span>task (pattern, execution)](#apidoc.element.node-cron.task)
1.  object <span class="apidocSignatureSpan">node-cron.</span>scheduled_task.prototype
1.  object <span class="apidocSignatureSpan">node-cron.</span>task.prototype

#### [module node-cron.scheduled_task](#apidoc.module.node-cron.scheduled_task)
1.  [function <span class="apidocSignatureSpan">node-cron.</span>scheduled_task (task, immediateStart)](#apidoc.element.node-cron.scheduled_task.scheduled_task)

#### [module node-cron.scheduled_task.prototype](#apidoc.module.node-cron.scheduled_task.prototype)
1.  [function <span class="apidocSignatureSpan">node-cron.scheduled_task.prototype.</span>destroy ()](#apidoc.element.node-cron.scheduled_task.prototype.destroy)
1.  [function <span class="apidocSignatureSpan">node-cron.scheduled_task.prototype.</span>start ()](#apidoc.element.node-cron.scheduled_task.prototype.start)
1.  [function <span class="apidocSignatureSpan">node-cron.scheduled_task.prototype.</span>stop ()](#apidoc.element.node-cron.scheduled_task.prototype.stop)

#### [module node-cron.task](#apidoc.module.node-cron.task)
1.  [function <span class="apidocSignatureSpan">node-cron.</span>task (pattern, execution)](#apidoc.element.node-cron.task.task)

#### [module node-cron.task.prototype](#apidoc.module.node-cron.task.prototype)
1.  [function <span class="apidocSignatureSpan">node-cron.task.prototype.</span>update (date)](#apidoc.element.node-cron.task.prototype.update)



# <a name="apidoc.module.node-cron"></a>[module node-cron](#apidoc.module.node-cron)

#### <a name="apidoc.element.node-cron.schedule"></a>[function <span class="apidocSignatureSpan">node-cron.</span>schedule (expression, func, immediateStart)](#apidoc.element.node-cron.schedule)
- description and source-code
```javascript
function createTask(expression, func, immediateStart) {
  var task = new Task(expression, func);

  return new ScheduledTask(task, immediateStart);
}
```
- example usage
```shell
...
'''

Import node-cron and schedule a task:

'''javascript
var cron = require('node-cron');

cron.schedule('* * * * *', function(){
  console.log('running a task every minute');
});
'''

## Cron Syntax

This is a quick reference to cron syntax and also shows the options supported by node-cron.
...
```

#### <a name="apidoc.element.node-cron.scheduled_task"></a>[function <span class="apidocSignatureSpan">node-cron.</span>scheduled_task (task, immediateStart)](#apidoc.element.node-cron.scheduled_task)
- description and source-code
```javascript
function ScheduledTask(task, immediateStart) {
  this.task = function() {
    task.update(new Date());
  };

  this.tick = null;

  if (immediateStart !== false) {
    this.start();
  }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.node-cron.task"></a>[function <span class="apidocSignatureSpan">node-cron.</span>task (pattern, execution)](#apidoc.element.node-cron.task)
- description and source-code
```javascript
function Task(pattern, execution){
  validatePattern(pattern);
  this.initialPattern = pattern.split(' ');
  this.pattern = convertExpression(pattern);
  this.execution = execution;
  this.expressions = this.pattern.split(' ');
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.node-cron.scheduled_task"></a>[module node-cron.scheduled_task](#apidoc.module.node-cron.scheduled_task)

#### <a name="apidoc.element.node-cron.scheduled_task.scheduled_task"></a>[function <span class="apidocSignatureSpan">node-cron.</span>scheduled_task (task, immediateStart)](#apidoc.element.node-cron.scheduled_task.scheduled_task)
- description and source-code
```javascript
function ScheduledTask(task, immediateStart) {
  this.task = function() {
    task.update(new Date());
  };

  this.tick = null;

  if (immediateStart !== false) {
    this.start();
  }
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.node-cron.scheduled_task.prototype"></a>[module node-cron.scheduled_task.prototype](#apidoc.module.node-cron.scheduled_task.prototype)

#### <a name="apidoc.element.node-cron.scheduled_task.prototype.destroy"></a>[function <span class="apidocSignatureSpan">node-cron.scheduled_task.prototype.</span>destroy ()](#apidoc.element.node-cron.scheduled_task.prototype.destroy)
- description and source-code
```javascript
destroy = function () {
  this.stop();

  this.task = null;
}
```
- example usage
```shell
...
'''javascript
var cron = require('node-cron');

var task = cron.schedule('* * * * *', function() {
  console.log('will not execute anymore, nor be able to restart');
});

task.destroy();
'''

## Issues

Feel free to submit issues and enhancement requests [here](https://github.com/merencia/node-cron/issues).

## Contributors
...
```

#### <a name="apidoc.element.node-cron.scheduled_task.prototype.start"></a>[function <span class="apidocSignatureSpan">node-cron.scheduled_task.prototype.</span>start ()](#apidoc.element.node-cron.scheduled_task.prototype.start)
- description and source-code
```javascript
start = function () {
  if (this.task && !this.tick) {
    this.tick = setInterval(this.task, 1000);
  }

  return this;
}
```
- example usage
```shell
...
'''javascript
var cron = require('node-cron');

var task = cron.schedule('* * * * *', function() {
  console.log('immediately started');
}, false);

task.start();
'''

### Stop

The task won't be executed unless re-started.

'''javascript
...
```

#### <a name="apidoc.element.node-cron.scheduled_task.prototype.stop"></a>[function <span class="apidocSignatureSpan">node-cron.scheduled_task.prototype.</span>stop ()](#apidoc.element.node-cron.scheduled_task.prototype.stop)
- description and source-code
```javascript
stop = function () {
  if (this.tick) {
    clearInterval(this.tick);
    this.tick = null;
  }

  return this;
}
```
- example usage
```shell
...
'''javascript
var cron = require('node-cron');

var task = cron.schedule('* * * * *', function() {
  console.log('will execute every minute until stopped');
});

task.stop();
'''

### Destroy

The task will be stopped and completely destroyed.

'''javascript
...
```



# <a name="apidoc.module.node-cron.task"></a>[module node-cron.task](#apidoc.module.node-cron.task)

#### <a name="apidoc.element.node-cron.task.task"></a>[function <span class="apidocSignatureSpan">node-cron.</span>task (pattern, execution)](#apidoc.element.node-cron.task.task)
- description and source-code
```javascript
function Task(pattern, execution){
  validatePattern(pattern);
  this.initialPattern = pattern.split(' ');
  this.pattern = convertExpression(pattern);
  this.execution = execution;
  this.expressions = this.pattern.split(' ');
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.node-cron.task.prototype"></a>[module node-cron.task.prototype](#apidoc.module.node-cron.task.prototype)

#### <a name="apidoc.element.node-cron.task.prototype.update"></a>[function <span class="apidocSignatureSpan">node-cron.task.prototype.</span>update (date)](#apidoc.element.node-cron.task.prototype.update)
- description and source-code
```javascript
update = function (date){
  if(mustRun(this, date)){
    try {
      this.execution();
    } catch(err) {
      console.error(err);
    }
  }
}
```
- example usage
```shell
...
   * Creates a new scheduled task.
   *
   * @param {Task} task - task to schedule.
   * @param {boolean} immediateStart - whether to start the task immediately.
   */
  function ScheduledTask(task, immediateStart) {
this.task = function() {
  task.update(new Date());
};

this.tick = null;

if (immediateStart !== false) {
  this.start();
}
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
