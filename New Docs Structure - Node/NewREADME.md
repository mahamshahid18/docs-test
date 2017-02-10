# Getting Started with TesterLib


## How to Use

The following section explains how to use the TesterLib library in a new project.




## Initializing

The API client can be initialized as following.

```js
var lib = require('lib');
```

## API Reference

### List of APIs

* [QueryParamController](#queryparamcontroller)
* [HeaderController](#headercontroller)
* [FormParamsController](#formparamscontroller)
* [ErrorCodesController](#errorcodescontroller)
* [ResponseTypesController](#responsetypescontroller)
* [TemplateParamsController](#templateparamscontroller)
* [EchoController](#echocontroller)
* [BodyParamsController](#bodyparamscontroller)

### `QueryParamController`

#### `multipleParams`

```js
function multipleParams( number, precision, string, url, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `number` | Required | - |
| `precision` | Required | - |
| `string` | Required | - |
| `url` | Required | - |

##### Example Usage

```js
var number = 123412312;
    var precision = 1112.34;
    var string = "\"\"test./;\";12&&3asl\"\";\"qw1&34\"///..//.";
    var url = "http://www.abc.com/test?a=b&c=\"http://lolol.com?param=no&another=lol\"";
controller.multipleParams(number, precision, string, url, function(error, response, context) {

}
```

#### `simpleQuery`

```js
function simpleQuery( mboolean, number, string, queryParameters, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `mboolean` | Required | - |
| `number` | Required | - |
| `string` | Required | - |

##### Example Usage

```js
var mboolean = true;
    var number = 4;
    var string = "TestString";

    // key-value map for optional query parameters
    var queryParameters = [];
controller.simpleQuery(mboolean, number, string, queryParameters, function(error, response, context) {

}
```

#### `stringEnumArray`

```js
function stringEnumArray( days, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `days` | Required, Collection | - |

##### Example Usage

```js
var days = ["Tuesday", "Saturday", "Wednesday", "Monday", "Sunday"];
controller.stringEnumArray(days, function(error, response, context) {

}
```

#### `stringArray`

```js
function stringArray( strings, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `strings` | Required, Collection | - |

##### Example Usage

```js
var strings = ["abc", "def"];
controller.stringArray(strings, function(error, response, context) {

}
```

#### `numberArray`

```js
function numberArray( integers, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `integers` | Required, Collection | - |

##### Example Usage

```js
var integers = [1,2,3,4,5];
controller.numberArray(integers, function(error, response, context) {

}
```

#### `integerEnumArray`

```js
function integerEnumArray( suites, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `suites` | Required, Collection | - |

##### Example Usage

```js
var suites = [1, 3, 4, 2, 3];
controller.integerEnumArray(suites, function(error, response, context) {

}
```

#### `urlParam`

```js
function urlParam( url, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `url` | Required | - |

##### Example Usage

```js
var url = "https://www.shahidisawesome.com/and/also/a/narcissist?thisis=aparameter&another=one";
controller.urlParam(url, function(error, response, context) {

}
```

#### `stringParam`

```js
function stringParam( string, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `string` | Required | - |

##### Example Usage

```js
var string = "l;asd;asdwe[2304&&;'.d??\\a\\\\\\;sd//";
controller.stringParam(string, function(error, response, context) {

}
```

#### `noParams`

```js
function noParams(callback)
```

##### Example Usage

```js
controller.noParams(function(error, response, context) {

}
```

### `HeaderController`

#### `sendHeaders`

Sends a single header params

```js
function sendHeaders( customHeader, value, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `customHeader` | Required | - |
| `value` | Required | Represents the value of the custom header |

##### Example Usage

```js
var customHeader = "TestString";
    var value = "TestString";
controller.sendHeaders(customHeader, value, function(error, response, context) {

}
```

### `FormParamsController`

#### `sendMixedArray`

Send a variety for form params. Returns file count and body params

```js
function sendMixedArray( options, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `file` | Required | - |
| `integers` | Required, Collection | - |
| `models` | Required, Collection | - |
| `strings` | Required, Collection | - |

##### Example Usage

```js
TestHelper.getFilePath("https://dl.dropboxusercontent.com/u/31838656/binary.png", function(data) {
        var input = [];
        input["file"] = data;
        input["integers"] = [1,2,3,4,5];
        input["models"] = [{"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]}, {"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]}].map(function(elem) {
        return new Employee(elem);
    });
        input["strings"] = ["abc", "def"];
    controller.sendMixedArray(input, function(error, response, context) {

}
```

#### `sendFile`

```js
function sendFile( file, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `file` | Required | - |

##### Example Usage

```js
TestHelper.getFilePath("https://dl.dropboxusercontent.com/u/31838656/binary.png", function(data) {
        var file = data;
    controller.sendFile(file, function(error, response, context) {

}
```

#### `sendModelArray`

```js
function sendModelArray( models, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `models` | Required, Collection | - |

##### Example Usage

```js
var models = [{"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]}, {"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]}].map(function(elem) {
        return new Employee(elem);
    });
controller.sendModelArray(models, function(error, response, context) {

}
```

#### `sendModel`

```js
function sendModel( model, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `model` | Required | - |

##### Example Usage

```js
var model = new Employee({"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]});
controller.sendModel(model, function(error, response, context) {

}
```

#### `sendStringEnumArray`

```js
function sendStringEnumArray( days, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `days` | Required, Collection | - |

##### Example Usage

```js
var days = ["Tuesday", "Saturday", "Wednesday", "Monday", "Sunday"];
controller.sendStringEnumArray(days, function(error, response, context) {

}
```

#### `sendIntegerEnumArray`

```js
function sendIntegerEnumArray( suites, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `suites` | Required, Collection | - |

##### Example Usage

```js
var suites = [1, 3, 4, 2, 3];
controller.sendIntegerEnumArray(suites, function(error, response, context) {

}
```

#### `sendStringArray`

```js
function sendStringArray( strings, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `strings` | Required, Collection | - |

##### Example Usage

```js
var strings = ["abc", "def"];
controller.sendStringArray(strings, function(error, response, context) {

}
```

#### `sendIntegerArray`

```js
function sendIntegerArray( integers, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `integers` | Required, Collection | - |

##### Example Usage

```js
var integers = [1,2,3,4,5];
controller.sendIntegerArray(integers, function(error, response, context) {

}
```

#### `sendString`

```js
function sendString( value, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `value` | Required | - |

##### Example Usage

```js
var value = "TestString";
controller.sendString(value, function(error, response, context) {

}
```

#### `sendLong`

```js
function sendLong( value, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `value` | Required | - |

##### Example Usage

```js
var value = 5147483647;
controller.sendLong(value, function(error, response, context) {

}
```

### `ErrorCodesController`

#### `get401`

```js
function get401(callback)
```

##### Example Usage

```js
controller.get401(function(error, response, context) {

}
```

##### Errors

| HTTP Status Code | Error Description |
|  --- | --- |
| 401 | 401 Local |
| 402 | Default |
| 403 | Default |
| 500 | Default |
| 509 | Default |
| Default | Invalid response. |

#### `get500`

```js
function get500(callback)
```

##### Example Usage

```js
controller.get500(function(error, response, context) {

}
```

#### `get400`

```js
function get400(callback)
```

##### Example Usage

```js
controller.get400(function(error, response, context) {

}
```

### `ResponseTypesController`

#### `getBinary`

gets a binary object

```js
function getBinary(callback)
```

##### Example Usage

```js
controller.getBinary(function(error, response, context) {

}
```

#### `getPrecision`

```js
function getPrecision(callback)
```

##### Example Usage

```js
controller.getPrecision(function(error, response, context) {

}
```

#### `getIntEnumArray`

```js
function getIntEnumArray(callback)
```

##### Example Usage

```js
controller.getIntEnumArray(function(error, response, context) {

}
```

#### `getIntEnum`

```js
function getIntEnum(callback)
```

##### Example Usage

```js
controller.getIntEnum(function(error, response, context) {

}
```

#### `getModelArray`

```js
function getModelArray(callback)
```

##### Example Usage

```js
controller.getModelArray(function(error, response, context) {

}
```

#### `getStringEnum`

```js
function getStringEnum(callback)
```

##### Example Usage

```js
controller.getStringEnum(function(error, response, context) {

}
```

#### `getStringEnumArray`

```js
function getStringEnumArray(callback)
```

##### Example Usage

```js
controller.getStringEnumArray(function(error, response, context) {

}
```

#### `getModel`

```js
function getModel(callback)
```

##### Example Usage

```js
controller.getModel(function(error, response, context) {

}
```

#### `getLong`

```js
function getLong(callback)
```

##### Example Usage

```js
controller.getLong(function(error, response, context) {

}
```

#### `getHeaders`

```js
function getHeaders(callback)
```

##### Example Usage

```js
controller.getHeaders(function(error, response, context) {

}
```

#### `getBooleanArray`

```js
function getBooleanArray(callback)
```

##### Example Usage

```js
controller.getBooleanArray(function(error, response, context) {

}
```

#### `getBoolean`

```js
function getBoolean(callback)
```

##### Example Usage

```js
controller.getBoolean(function(error, response, context) {

}
```

#### `getDatetimeArray`

```js
function getDatetimeArray(callback)
```

##### Example Usage

```js
controller.getDatetimeArray(function(error, response, context) {

}
```

#### `getDatetime`

```js
function getDatetime(callback)
```

##### Example Usage

```js
controller.getDatetime(function(error, response, context) {

}
```

#### `getDynamicArray`

```js
function getDynamicArray(callback)
```

##### Example Usage

```js
controller.getDynamicArray(function(error, response, context) {

}
```

#### `getDynamic`

```js
function getDynamic(callback)
```

##### Example Usage

```js
controller.getDynamic(function(error, response, context) {

}
```

#### `getIntegerArray`

Get an array of integers.

```js
function getIntegerArray(callback)
```

##### Example Usage

```js
controller.getIntegerArray(function(error, response, context) {

}
```

#### `getInteger`

Gets a integer response

```js
function getInteger(callback)
```

##### Example Usage

```js
controller.getInteger(function(error, response, context) {

}
```

### `TemplateParamsController`

#### `sendIntegerArray`

```js
function sendIntegerArray( integers, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `integers` | Required, Collection | - |

##### Example Usage

```js
var integers = [1,2,3,4,5];
controller.sendIntegerArray(integers, function(error, response, context) {

}
```

#### `sendStringArray`

```js
function sendStringArray( strings, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `strings` | Required, Collection | - |

##### Example Usage

```js
var strings = ["abc", "def"];
controller.sendStringArray(strings, function(error, response, context) {

}
```

### `EchoController`

#### `queryEcho`

```js
function queryEcho( queryParameters, callback)
```

##### Example Usage

```js
// key-value map for optional query parameters
    var queryParameters = [];
controller.queryEcho(queryParameters, function(error, response, context) {

}
```

#### `formEcho`

Sends the request including any form params as JSON

```js
function formEcho( input, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `input` | Required | - |

##### Example Usage

```js
var input = {"uid": "1123213", "name": "Shahid"};
controller.formEcho(input, function(error, response, context) {

}
```

#### `jsonEcho`

Echo's back the request

```js
function jsonEcho( input, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `input` | Required | - |

##### Example Usage

```js
var input = {"uid": "1123213", "name": "Shahid"};
controller.jsonEcho(input, function(error, response, context) {

}
```

### `BodyParamsController`

#### `sendIntegerEnumArray`

```js
function sendIntegerEnumArray( suites, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `suites` | Required, Collection | - |

##### Example Usage

```js
var suites = [1, 3, 4, 2, 3];
controller.sendIntegerEnumArray(suites, function(error, response, context) {

}
```

#### `sendStringEnumArray`

```js
function sendStringEnumArray( days, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `days` | Required, Collection | - |

##### Example Usage

```js
var days = ["Tuesday", "Saturday", "Wednesday", "Monday", "Sunday"];
controller.sendStringEnumArray(days, function(error, response, context) {

}
```

#### `sendString`

```js
function sendString( value, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `value` | Required | - |

##### Example Usage

```js
var value = "TestString";
controller.sendString(value, function(error, response, context) {

}
```

#### `sendDynamic`

```js
function sendDynamic( dynamic, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `dynamic` | Required | - |

##### Example Usage

```js
var dynamic = {"uid": "1123213", "name": "Shahid"};
controller.sendDynamic(dynamic, function(error, response, context) {

}
```

#### `sendModelArray`

```js
function sendModelArray( models, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `models` | Required, Collection | - |

##### Example Usage

```js
var models = [{"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]}, {"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]}].map(function(elem) {
        return new Employee(elem);
    });
controller.sendModelArray(models, function(error, response, context) {

}
```

#### `sendModel`

```js
function sendModel( model, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `model` | Required | - |

##### Example Usage

```js
var model = new Employee({"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]});
controller.sendModel(model, function(error, response, context) {

}
```

#### `sendIntegerArray`

```js
function sendIntegerArray( integers, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `integers` | Required, Collection | - |

##### Example Usage

```js
var integers = [1,2,3,4,5];
controller.sendIntegerArray(integers, function(error, response, context) {

}
```

#### `sendStringArray`

sends a string body param

```js
function sendStringArray( sarray, callback)
```

##### Parameters

| Parameter | Tags | Description |
|  --- | --- | --- |
| `sarray` | Required, Collection | - |

##### Example Usage

```js
var sarray = ["abc", "def"];
controller.sendStringArray(sarray, function(error, response, context) {

}
```

## Model Reference

### Structures

* [`EchoResponse`](#`echoresponse`)
* [`QueryParameter`](#`queryparameter`)
* [`Employee` (extends `Person`)](#`employee`-(extends-`person`))
* [`ServerResponse`](#`serverresponse`)
* [`Person`](#`person`)

#### `EchoResponse`

Raw http Request info

##### Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | `dictionary|null` | Optional | - |
| `headers` | `dictionary|null` | Optional | - |
| `method` | `string|null` | Optional | - |
| `path` | `string|null` | Optional | relativePath |
| `query` | `dictionary|null` | Optional | - |
| `uploadCount` | `int|null` | Optional | - |

##### Example

```js
Model code sample is currently being worked on
```

#### `QueryParameter`

Query parameter key value pair echoed back from the server.

##### Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `key` | `string|null` | Optional | - |

##### Example

```js
Model code sample is currently being worked on
```

#### `Employee` (extends `Person`)

##### Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `boss` | `Person` |  | - |
| `department` | `string` |  | - |
| `dependents` | `Person[]` |  | - |
| `joiningDay` | `Days` |  | *Default:*`"Monday"` |
| `salary` | `int` |  | - |
| `workingDays` | `array` |  | - |

##### Example

```js
Model code sample is currently being worked on
```

#### `ServerResponse`

##### Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `passed` | `bool` |  | - |
| `message` | `string|null` | Optional | - |
| `input` | `dictionary|null` | Optional | - |

##### Example

```js
Model code sample is currently being worked on
```

#### `Person`

##### Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `address` | `string` |  | - |
| `age` | `long` |  | - |
| `name` | `string` |  | - |
| `uid` | `string` |  | - |

##### Example

```js
Model code sample is currently being worked on
```

### Enumerations

* [`Days`](#`days`)
* [`SuiteCode`](#`suitecode`)

#### `Days`

A string enum representing days of the week

##### Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `sunday` | `string` |  | *Value:*`"Sunday"` |
| `monday` | `string` |  | *Value:*`"Monday"` |
| `tuesday` | `string` |  | *Value:*`"Tuesday"` |
| `wednesday` | `string` |  | *Value:*`"Wednesday"` |
| `thursday` | `string` |  | *Value:*`"Thursday"` |
| `friDay` | `string` |  | *Value:*`"Friday"` |
| `saturday` | `string` |  | *Value:*`"Saturday"` |

##### Example

```js
Model code sample is currently being worked on
```

#### `SuiteCode`

A integer based enum representing a Suite in a game of cards

##### Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `hearts` | `int` |  | *Value:*`1` |
| `spades` | `int` |  | *Value:*`2` |
| `clubs` | `int` |  | *Value:*`3` |
| `diamonds` | `int` |  | *Value:*`4` |

##### Example

```js
Model code sample is currently being worked on
```

### Exceptions

* [`LocalTestException` (extends `GlobalTestException`)](#`localtestexception`-(extends-`globaltestexception`))
* [`GlobalTestException`](#`globaltestexception`)

#### `LocalTestException` (extends `GlobalTestException`)

To test specific local exceptions.

##### Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `secretMessageForEndpoint` | `string` |  | Represents the specific endpoint info |

##### Example

```js
Model code sample is currently being worked on
```

#### `GlobalTestException`

To test specific global exceptions.

##### Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `serverMessage` | `string` |  | Represents the server's exception message |
| `serverCode` | `int` |  | Represents the server's error code |

##### Example

```js
Model code sample is currently being worked on
```