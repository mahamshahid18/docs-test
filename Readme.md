#Getting started

## How to Build

The generated SDK relies on [Node Package Manager](https://www.npmjs.com/) (NPM) being available to resolve dependencies. If you don't already have NPM installed, please go ahead and follow instructions to install NPM from [here](https://nodejs.org/en/download/).
The SDK also requires Node to be installed. If Node isn't already installed, please install it from [here](https://nodejs.org/en/download/)
> NPM is installed by default when Node is installed

To check if node and npm have been successfully installed, write the following commands in command prompt:
* `node --version`
* `npm -version`   

Now use npm to resolve all dependencies by running the following command in the root directory (of the SDK folder):
* `npm install`

This will install all dependencies in the `node_modules` folder.  
Once dependencies are resolved, you will need to move the folder `Tester ` in to your `node_modules` folder.

## How to Use

The following section explains how to use the library in a new project.

### 1. Open Project Folder
Open an IDE/Text Editor for JavaScript like Sublime Text. The basic workflow presented here is also applicable if you prefer using a different editor or IDE.  
Click on `File` and select `Open Folder`

Select the folder of your SDK and click on `Select Folder` to open it up in Sublime Text. The folder will become visible in the bar on the left.


### 2. Creating a Test File
Now right click on the folder name and select the `New File` option to create a new test file.    Save it as `index.js` Now import the generated NodeJS library using the following lines of code:
```JavaScript
var lib = require('lib');
```
Save changes.

### 3. Running The Test File
To run the `index.js` file, open up the command prompt and navigate to the Path where the SDK folder resides. Type the following command to run the file:  
`node index.js`


## How to Test

These tests use Mocha framework for testing, coupled with Chai for assertions. These dependencies need to be installed for tests to run.
Tests can be run in a number of ways:

### Method 1 
###### (Run all tests)

1. Navigate to the root directory of the SDK folder from command prompt.
2. Type `mocha --recursive` to run all the tests.

### Method 2
###### (Run all tests)

1. Navigate to the `../test/Controllers/` directory from command prompt.
2. Type `mocha *` to run all the tests.

### Method 3
###### (Run specific controller's tests)

1. Navigate to the `../test/Controllers/` directory from command prompt.
2. Type `mocha  Tester`  to run all the tests in that controller file.

> To increase mocha's default timeout, you can change the `TESTTIMEOUT` parameter's value in `Configuration.js`.  
> ***NOTE:*** Changing default timeout is available for only Binary/File type endpoint tests

## Initialization

### 

API client can be initialized as following:

```JavaScript

var lib = require('lib');
```

## Class Reference

### <a name="list_of_controllers"></a>List of Controllers

* [ResponseTypesController](#response_types_controller)
* [ErrorCodesController](#error_codes_controller)
* [BodyParamsController](#body_params_controller)
* [FormParamsController](#form_params_controller)
* [EchoController](#echo_controller)
* [HeaderController](#header_controller)
* [QueryParamController](#query_param_controller)
* [TemplateParamsController](#template_params_controller)

### <a name="response_types_controller"></a>![Class: ](http://apidocs.io/img/class.png ".ResponseTypesController") ResponseTypesController

#### Get singleton instance

The singleton instance of the ``` ResponseTypesController ``` class can be accessed from the API Client.

```javascript
var controller = lib.ResponseTypesController;
```

#### <a name="get_long"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getLong") getLong

> TODO: Add a method description


```javascript
function getLong(callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|



#### Example Usage

```javascript

    
    controller.getLong(function(error, response, context) {

            
    });
```


#### <a name="get_model"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getModel") getModel

> TODO: Add a method description


```javascript
function getModel(callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|



#### Example Usage

```javascript

    
    controller.getModel(function(error, response, context) {

            
    });
```


#### <a name="get_string_enum_array"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getStringEnumArray") getStringEnumArray

> TODO: Add a method description


```javascript
function getStringEnumArray(callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|



#### Example Usage

```javascript

    
    controller.getStringEnumArray(function(error, response, context) {

            
    });
```


#### <a name="get_string_enum"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getStringEnum") getStringEnum

> TODO: Add a method description


```javascript
function getStringEnum(callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|



#### Example Usage

```javascript

    
    controller.getStringEnum(function(error, response, context) {

            
    });
```


#### <a name="get_model_array"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getModelArray") getModelArray

> TODO: Add a method description


```javascript
function getModelArray(callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|



#### Example Usage

```javascript

    
    controller.getModelArray(function(error, response, context) {

            
    });
```


#### <a name="get_int_enum"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getIntEnum") getIntEnum

> TODO: Add a method description


```javascript
function getIntEnum(callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|



#### Example Usage

```javascript

    
    controller.getIntEnum(function(error, response, context) {

            
    });
```


#### <a name="get_int_enum_array"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getIntEnumArray") getIntEnumArray

> TODO: Add a method description


```javascript
function getIntEnumArray(callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|



#### Example Usage

```javascript

    
    controller.getIntEnumArray(function(error, response, context) {

            
    });
```


#### <a name="get_precision"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getPrecision") getPrecision

> TODO: Add a method description


```javascript
function getPrecision(callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|



#### Example Usage

```javascript

    
    controller.getPrecision(function(error, response, context) {

            
    });
```


#### <a name="get_binary"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getBinary") getBinary

> gets a binary object


```javascript
function getBinary(callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|



#### Example Usage

```javascript

    
    TestHelper.getFileContents("https://dl.dropboxusercontent.com/u/31838656/binary.png", function(data) {
    controller.getBinary(function(error, response, context) {

            
    });
```


#### <a name="get_integer"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getInteger") getInteger

> Gets a integer response


```javascript
function getInteger(callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|



#### Example Usage

```javascript

    
    controller.getInteger(function(error, response, context) {

            
    });
```


#### <a name="get_integer_array"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getIntegerArray") getIntegerArray

> Get an array of integers.


```javascript
function getIntegerArray(callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|



#### Example Usage

```javascript

    
    controller.getIntegerArray(function(error, response, context) {

            
    });
```


#### <a name="get_dynamic"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getDynamic") getDynamic

> TODO: Add a method description


```javascript
function getDynamic(callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|



#### Example Usage

```javascript

    
    controller.getDynamic(function(error, response, context) {

            
    });
```


#### <a name="get_dynamic_array"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getDynamicArray") getDynamicArray

> TODO: Add a method description


```javascript
function getDynamicArray(callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|



#### Example Usage

```javascript

    
    controller.getDynamicArray(function(error, response, context) {

            
    });
```


#### <a name="get_datetime"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getDatetime") getDatetime

> TODO: Add a method description


```javascript
function getDatetime(callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|



#### Example Usage

```javascript

    
    controller.getDatetime(function(error, response, context) {

            
    });
```


#### <a name="get_datetime_array"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getDatetimeArray") getDatetimeArray

> TODO: Add a method description


```javascript
function getDatetimeArray(callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|



#### Example Usage

```javascript

    
    controller.getDatetimeArray(function(error, response, context) {

            
    });
```


#### <a name="get_boolean"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getBoolean") getBoolean

> TODO: Add a method description


```javascript
function getBoolean(callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|



#### Example Usage

```javascript

    
    controller.getBoolean(function(error, response, context) {

            
    });
```


#### <a name="get_boolean_array"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getBooleanArray") getBooleanArray

> TODO: Add a method description


```javascript
function getBooleanArray(callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|



#### Example Usage

```javascript

    
    controller.getBooleanArray(function(error, response, context) {

            
    });
```


#### <a name="get_headers"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getHeaders") getHeaders

> TODO: Add a method description


```javascript
function getHeaders(callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|



#### Example Usage

```javascript

    
    controller.getHeaders(function(error, response, context) {

            
    });
```


[Back to List of Controllers](#list_of_controllers)

### <a name="error_codes_controller"></a>![Class: ](http://apidocs.io/img/class.png ".ErrorCodesController") ErrorCodesController

#### Get singleton instance

The singleton instance of the ``` ErrorCodesController ``` class can be accessed from the API Client.

```javascript
var controller = lib.ErrorCodesController;
```

#### <a name="get400"></a>![Method: ](http://apidocs.io/img/method.png ".ErrorCodesController.get400") get400

> TODO: Add a method description


```javascript
function get400(callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|



#### Example Usage

```javascript

    
    controller.get400(function(error, response, context) {

            
    });
```


#### <a name="get500"></a>![Method: ](http://apidocs.io/img/method.png ".ErrorCodesController.get500") get500

> TODO: Add a method description


```javascript
function get500(callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|



#### Example Usage

```javascript

    
    controller.get500(function(error, response, context) {

            
    });
```


#### <a name="get401"></a>![Method: ](http://apidocs.io/img/method.png ".ErrorCodesController.get401") get401

> TODO: Add a method description


```javascript
function get401(callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|



#### Example Usage

```javascript

    
    controller.get401(function(error, response, context) {

            
    });
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | 401 Local |



[Back to List of Controllers](#list_of_controllers)

### <a name="body_params_controller"></a>![Class: ](http://apidocs.io/img/class.png ".BodyParamsController") BodyParamsController

#### Get singleton instance

The singleton instance of the ``` BodyParamsController ``` class can be accessed from the API Client.

```javascript
var controller = lib.BodyParamsController;
```

#### <a name="send_string_array"></a>![Method: ](http://apidocs.io/img/method.png ".BodyParamsController.sendStringArray") sendStringArray

> sends a string body param


```javascript
function sendStringArray(sarray, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| sarray |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var sarray = ["abc", "def"];

    controller.sendStringArray(sarray, function(error, response, context) {

            
    });
```


#### <a name="send_integer_array"></a>![Method: ](http://apidocs.io/img/method.png ".BodyParamsController.sendIntegerArray") sendIntegerArray

> TODO: Add a method description


```javascript
function sendIntegerArray(integers, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| integers |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var integers = [1,2,3,4,5];

    controller.sendIntegerArray(integers, function(error, response, context) {

            
    });
```


#### <a name="send_model"></a>![Method: ](http://apidocs.io/img/method.png ".BodyParamsController.sendModel") sendModel

> TODO: Add a method description


```javascript
function sendModel(model, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| model |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var model = new Employee({"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]});

    controller.sendModel(model, function(error, response, context) {

            
    });
```


#### <a name="send_model_array"></a>![Method: ](http://apidocs.io/img/method.png ".BodyParamsController.sendModelArray") sendModelArray

> TODO: Add a method description


```javascript
function sendModelArray(models, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| models |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var models = [{"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]}, {"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]}].map(function(elem) {
        return new Employee(elem);
    });

    controller.sendModelArray(models, function(error, response, context) {

            
    });
```


#### <a name="send_dynamic"></a>![Method: ](http://apidocs.io/img/method.png ".BodyParamsController.sendDynamic") sendDynamic

> TODO: Add a method description


```javascript
function sendDynamic(dynamic, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| dynamic |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var dynamic = {"uid": "1123213", "name": "Shahid"};

    controller.sendDynamic(dynamic, function(error, response, context) {

            
    });
```


#### <a name="send_string"></a>![Method: ](http://apidocs.io/img/method.png ".BodyParamsController.sendString") sendString

> TODO: Add a method description


```javascript
function sendString(value, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| value |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var value = "TestString";

    controller.sendString(value, function(error, response, context) {

            
    });
```


#### <a name="send_string_enum_array"></a>![Method: ](http://apidocs.io/img/method.png ".BodyParamsController.sendStringEnumArray") sendStringEnumArray

> TODO: Add a method description


```javascript
function sendStringEnumArray(days, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| days |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var days = ["Tuesday", "Saturday", "Wednesday", "Monday", "Sunday"];

    controller.sendStringEnumArray(days, function(error, response, context) {

            
    });
```


#### <a name="send_integer_enum_array"></a>![Method: ](http://apidocs.io/img/method.png ".BodyParamsController.sendIntegerEnumArray") sendIntegerEnumArray

> TODO: Add a method description


```javascript
function sendIntegerEnumArray(suites, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| suites |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var suites = [1, 3, 4, 2, 3];

    controller.sendIntegerEnumArray(suites, function(error, response, context) {

            
    });
```


[Back to List of Controllers](#list_of_controllers)

### <a name="form_params_controller"></a>![Class: ](http://apidocs.io/img/class.png ".FormParamsController") FormParamsController

#### Get singleton instance

The singleton instance of the ``` FormParamsController ``` class can be accessed from the API Client.

```javascript
var controller = lib.FormParamsController;
```

#### <a name="send_long"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendLong") sendLong

> TODO: Add a method description


```javascript
function sendLong(value, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| value |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var value = 5147483647;

    controller.sendLong(value, function(error, response, context) {

            
    });
```


#### <a name="send_integer_array"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendIntegerArray") sendIntegerArray

> TODO: Add a method description


```javascript
function sendIntegerArray(integers, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| integers |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var integers = [1,2,3,4,5];

    controller.sendIntegerArray(integers, function(error, response, context) {

            
    });
```


#### <a name="send_string_array"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendStringArray") sendStringArray

> TODO: Add a method description


```javascript
function sendStringArray(strings, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| strings |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var strings = ["abc", "def"];

    controller.sendStringArray(strings, function(error, response, context) {

            
    });
```


#### <a name="send_model"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendModel") sendModel

> TODO: Add a method description


```javascript
function sendModel(model, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| model |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var model = new Employee({"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]});

    controller.sendModel(model, function(error, response, context) {

            
    });
```


#### <a name="send_model_array"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendModelArray") sendModelArray

> TODO: Add a method description


```javascript
function sendModelArray(models, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| models |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var models = [{"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]}, {"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]}].map(function(elem) {
        return new Employee(elem);
    });

    controller.sendModelArray(models, function(error, response, context) {

            
    });
```


#### <a name="send_file"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendFile") sendFile

> TODO: Add a method description


```javascript
function sendFile(file, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| file |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

    TestHelper.getFilePath("https://dl.dropboxusercontent.com/u/31838656/binary.png", function(data) {    var file = data;

    
    controller.sendFile(file, function(error, response, context) {

            
    });
```


#### <a name="send_mixed_array"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendMixedArray") sendMixedArray

> Send a variety for form params. Returns file count and body params


```javascript
function sendMixedArray(input, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| file |  ``` Required ```  | TODO: Add a parameter description |
| integers |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |
| models |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |
| strings |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

    TestHelper.getFilePath("https://dl.dropboxusercontent.com/u/31838656/binary.png", function(data) {    var input = [];
    input["file"] = data;
    input["integers"] = [1,2,3,4,5];
    input["models"] = [{"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]}, {"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]}].map(function(elem) {
        return new Employee(elem);
    });
    input["strings"] = ["abc", "def"];

    
    controller.sendMixedArray(input, function(error, response, context) {

            
    });
```


#### <a name="send_string"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendString") sendString

> TODO: Add a method description


```javascript
function sendString(value, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| value |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var value = "TestString";

    controller.sendString(value, function(error, response, context) {

            
    });
```


#### <a name="send_integer_enum_array"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendIntegerEnumArray") sendIntegerEnumArray

> TODO: Add a method description


```javascript
function sendIntegerEnumArray(suites, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| suites |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var suites = [1, 3, 4, 2, 3];

    controller.sendIntegerEnumArray(suites, function(error, response, context) {

            
    });
```


#### <a name="send_string_enum_array"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendStringEnumArray") sendStringEnumArray

> TODO: Add a method description


```javascript
function sendStringEnumArray(days, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| days |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var days = ["Tuesday", "Saturday", "Wednesday", "Monday", "Sunday"];

    controller.sendStringEnumArray(days, function(error, response, context) {

            
    });
```


[Back to List of Controllers](#list_of_controllers)

### <a name="echo_controller"></a>![Class: ](http://apidocs.io/img/class.png ".EchoController") EchoController

#### Get singleton instance

The singleton instance of the ``` EchoController ``` class can be accessed from the API Client.

```javascript
var controller = lib.EchoController;
```

#### <a name="json_echo"></a>![Method: ](http://apidocs.io/img/method.png ".EchoController.jsonEcho") jsonEcho

> Echo's back the request


```javascript
function jsonEcho(input, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| input |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var input = {"uid": "1123213", "name": "Shahid"};

    controller.jsonEcho(input, function(error, response, context) {

            
    });
```


#### <a name="form_echo"></a>![Method: ](http://apidocs.io/img/method.png ".EchoController.formEcho") formEcho

> Sends the request including any form params as JSON


```javascript
function formEcho(input, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| input |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var input = {"uid": "1123213", "name": "Shahid"};

    controller.formEcho(input, function(error, response, context) {

            
    });
```


#### <a name="query_echo"></a>![Method: ](http://apidocs.io/img/method.png ".EchoController.queryEcho") queryEcho

> TODO: Add a method description


```javascript
function queryEcho(queryParams, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| queryParameters | ``` Optional ``` | Additional optional query parameters are supported by this method |



#### Example Usage

```javascript

    
    // key-value map for optional query parameters
    var queryParams = [];

    controller.queryEcho(queryParams, function(error, response, context) {

            
    });
```


[Back to List of Controllers](#list_of_controllers)

### <a name="header_controller"></a>![Class: ](http://apidocs.io/img/class.png ".HeaderController") HeaderController

#### Get singleton instance

The singleton instance of the ``` HeaderController ``` class can be accessed from the API Client.

```javascript
var controller = lib.HeaderController;
```

#### <a name="send_headers"></a>![Method: ](http://apidocs.io/img/method.png ".HeaderController.sendHeaders") sendHeaders

> Sends a single header params


```javascript
function sendHeaders(customHeader, value, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| customHeader |  ``` Required ```  | TODO: Add a parameter description |
| value |  ``` Required ```  | Represents the value of the custom header |



#### Example Usage

```javascript

        var customHeader = "TestString";
    var value = "TestString";

    controller.sendHeaders(customHeader, value, function(error, response, context) {

            
    });
```


[Back to List of Controllers](#list_of_controllers)

### <a name="query_param_controller"></a>![Class: ](http://apidocs.io/img/class.png ".QueryParamController") QueryParamController

#### Get singleton instance

The singleton instance of the ``` QueryParamController ``` class can be accessed from the API Client.

```javascript
var controller = lib.QueryParamController;
```

#### <a name="simple_query"></a>![Method: ](http://apidocs.io/img/method.png ".QueryParamController.simpleQuery") simpleQuery

> TODO: Add a method description


```javascript
function simpleQuery(mboolean, number, string, queryParams, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mboolean |  ``` Required ```  | TODO: Add a parameter description |
| number |  ``` Required ```  | TODO: Add a parameter description |
| string |  ``` Required ```  | TODO: Add a parameter description |
| queryParameters | ``` Optional ``` | Additional optional query parameters are supported by this method |



#### Example Usage

```javascript

        var mboolean = true;
    var number = 4;
    var string = "TestString";

    // key-value map for optional query parameters
    var queryParams = [];

    controller.simpleQuery(mboolean, number, string, queryParams, function(error, response, context) {

            
    });
```


#### <a name="no_params"></a>![Method: ](http://apidocs.io/img/method.png ".QueryParamController.noParams") noParams

> TODO: Add a method description


```javascript
function noParams(callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|



#### Example Usage

```javascript

    
    controller.noParams(function(error, response, context) {

            
    });
```


#### <a name="string_param"></a>![Method: ](http://apidocs.io/img/method.png ".QueryParamController.stringParam") stringParam

> TODO: Add a method description


```javascript
function stringParam(string, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| string |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var string = "l;asd;asdwe[2304&&;'.d??\\a\\\\\\;sd//";

    controller.stringParam(string, function(error, response, context) {

            
    });
```


#### <a name="url_param"></a>![Method: ](http://apidocs.io/img/method.png ".QueryParamController.urlParam") urlParam

> TODO: Add a method description


```javascript
function urlParam(url, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| url |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var url = "https://www.shahidisawesome.com/and/also/a/narcissist?thisis=aparameter&another=one";

    controller.urlParam(url, function(error, response, context) {

            
    });
```


#### <a name="multiple_params"></a>![Method: ](http://apidocs.io/img/method.png ".QueryParamController.multipleParams") multipleParams

> TODO: Add a method description


```javascript
function multipleParams(number, precision, string, url, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| number |  ``` Required ```  | TODO: Add a parameter description |
| precision |  ``` Required ```  | TODO: Add a parameter description |
| string |  ``` Required ```  | TODO: Add a parameter description |
| url |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var number = 123412312;
    var precision = 1112.34;
    var string = "\"\"test./;\";12&&3asl\"\";\"qw1&34\"///..//.";
    var url = "http://www.abc.com/test?a=b&c=\"http://lolol.com?param=no&another=lol\"";

    controller.multipleParams(number, precision, string, url, function(error, response, context) {

            
    });
```


#### <a name="number_array"></a>![Method: ](http://apidocs.io/img/method.png ".QueryParamController.numberArray") numberArray

> TODO: Add a method description


```javascript
function numberArray(integers, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| integers |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var integers = [1,2,3,4,5];

    controller.numberArray(integers, function(error, response, context) {

            
    });
```


#### <a name="string_array"></a>![Method: ](http://apidocs.io/img/method.png ".QueryParamController.stringArray") stringArray

> TODO: Add a method description


```javascript
function stringArray(strings, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| strings |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var strings = ["abc", "def"];

    controller.stringArray(strings, function(error, response, context) {

            
    });
```


#### <a name="string_enum_array"></a>![Method: ](http://apidocs.io/img/method.png ".QueryParamController.stringEnumArray") stringEnumArray

> TODO: Add a method description


```javascript
function stringEnumArray(days, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| days |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var days = ["Tuesday", "Saturday", "Wednesday", "Monday", "Sunday"];

    controller.stringEnumArray(days, function(error, response, context) {

            
    });
```


#### <a name="integer_enum_array"></a>![Method: ](http://apidocs.io/img/method.png ".QueryParamController.integerEnumArray") integerEnumArray

> TODO: Add a method description


```javascript
function integerEnumArray(suites, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| suites |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var suites = [1, 3, 4, 2, 3];

    controller.integerEnumArray(suites, function(error, response, context) {

            
    });
```


[Back to List of Controllers](#list_of_controllers)

### <a name="template_params_controller"></a>![Class: ](http://apidocs.io/img/class.png ".TemplateParamsController") TemplateParamsController

#### Get singleton instance

The singleton instance of the ``` TemplateParamsController ``` class can be accessed from the API Client.

```javascript
var controller = lib.TemplateParamsController;
```

#### <a name="send_string_array"></a>![Method: ](http://apidocs.io/img/method.png ".TemplateParamsController.sendStringArray") sendStringArray

> TODO: Add a method description


```javascript
function sendStringArray(strings, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| strings |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var strings = ["abc", "def"];

    controller.sendStringArray(strings, function(error, response, context) {

            
    });
```


#### <a name="send_integer_array"></a>![Method: ](http://apidocs.io/img/method.png ".TemplateParamsController.sendIntegerArray") sendIntegerArray

> TODO: Add a method description


```javascript
function sendIntegerArray(integers, callback)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| integers |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

        var integers = [1,2,3,4,5];

    controller.sendIntegerArray(integers, function(error, response, context) {

            
    });
```


[Back to List of Controllers](#list_of_controllers)



