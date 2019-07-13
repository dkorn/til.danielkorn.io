---
title: "Skip Tests in Mocha"
date: 2019-07-12T10:41:39+03:00
draft: false
description: Dynamically skip JavaScript tests at runtime with Mocha
images: [/images/mocha.png]
tags: [test, JS, mocha, nodejs, skip, only, JavaScript, testing-framework, mochajs, dynamic, runtime]
keywords: [Test, JS, Mocha, Nodejs, skip, only, JavaScript, Testing Framework, Mochajs, dynamic, runtime]
---
[Mocha](https://mochajs.org) is a popular JavaScript test framework for [Node.js](https://nodejs.org/) & the browser.    
Unlike other test frameworks I've used before, it is really simple and quick to start with.

![Mochajs Banner](/images/mocha-banner.png)

One of the most common actions when writing or debugging tests, regardless of the framework used, is being able to **ignore** some tests.   
That is especially true if you practice TDD, or tend to first list the placeholders for the tests you plan to write.

This inclusive ability is available in Mocha by appending `.skip()` to the suite or to specific test
cases. The skipped tests will be marked as ["pending"](https://mochajs.org/#pending-tests) in the test results.

## Usage

```JavaScript
describe.skip('Filter', function() {
  // all suite will be skipped
});

describe('Filter', function() {
  it.skip('should filter values lower than 10', function() {
    // this test will *not* run
  });

  it('should filter undefined elements', function() {
    // this test will run
  });
});
```

Another quick option is prepending `x` to the `it` or the `describe`:

```JavaScript
xit('should filter all non-primary numbers', function() {
  // this test will be skipped
});

```

### Skipping tests programmatically at runtime 

In some situations, you'll need to skip tests dynamically.    
Example of such might be when the test depends on the running environment.

In this case use `this.skip()`

```JavaScript```
it('should only test in the development environment', function() {
  if (process.env.NODE_ENV === 'dev') {
    // assertions
  } else {
    this.skip();
  }
});

```

_Do not execute any action after calling_ `this.skip()`_, as the call will abort the test._

You can skip all tests in a describe block - including all `it`, `beforeEach`/`afterEach`, and `describe` blocks within the suite - by using `this.skip()` in a `before` hook

```JavaScript```
before(function() {
  if (process.env.NODE_ENV === 'dev') {
    // tests setup
  } else {
    this.skip();
  }
});
```

![Skip Tests Meme](/images/skip_tests_meme.JPG)

### Tip - Exclusive Tests

You can run just a specific suite or test-case by appending `.only()` to the function.

```JavaScript
describe.only('Filter', function() {
  // all tests in the suite will run
});

describe('Filter', function() {
  it.only('should filter values lower than 10', function() {
    // this test will run
  });
  
  it('should filter odd numbers', function() {
    // this test will not run
  });
});
```

## Mocha Installation

```shell
$ npm install -g mocha
```

