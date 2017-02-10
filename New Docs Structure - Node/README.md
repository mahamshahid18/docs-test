# TesterLib

This file was automatically generated for Stamplay by APIMATIC v2.0 ([https://apimatic.io](https://apimatic.io)) on 02-10-2017.

## Installation

The SDK relies on [Node Package Manager](https://www.npmjs.com/) (NPM) being available to resolve dependencies.
Once published you will need copy the folder `testerlib` in to your `node_modules` folder.

## Usage

The following shows how import and use the controller:

1. Import the module:

    ```js
    var testerlib = require('testerlib');
    ```

2. Access various controllers by:

    ```js
    var controller = testerlib.XYZ;
    controller.getItems(id, callback);
    ```

## Test

These tests use Mocha framework for testing, coupled with Chai for assertions. These dependencies need to be installed for tests to run.
Tests can be run in a number of ways:

### 

1. Navigate to the `../test/Controllers/` directory from command prompt.
2. Type `mocha XYZControllerTest` to run all the tests in that controller file.

###

1. Navigate to the `../test/Controllers/` directory from command prompt.
2. Type `mocha *` to run all the tests (from all the controller files).

###

1. Navigate to the root directory from command prompt. (/Node/)
2. Type `mocha --recursive` to run all the tests.
3. To increase mocha's default timeout, you can change the `TESTTIMEOUT` parameter's value in `Configuration.js`.

> NOTE: Changing default timeout is available for only Binary/File type endpoint tests
