#Getting started

## How to Build

The generated SDK requires AngularJS framework to work. If you do not already have angular downloaded, please go ahead and do it from [here](https://angularjs.org/)

## How to Use

The following section describes how to use the generate SDK in an existing/new project.

### 1. Configure Angular and Generated SDK
Perform the following steps to configure angular and the SDK:
+ Make a `scripts` folder inside the root folder of the project. If you already have one, skip to the next step.
+ Move the angular.min.js file inside the scripts folder. 
+ Move the generated-lib folder inside the scripts folder.

### 2. Open Project Folder
Open an IDE/Text Editor for JavaScript like Sublime Text. The basic workflow presented here is also applicable if you prefer using a different editor or IDE.
Click on `File` and select `Open Folder`
![open-folder-image]()

Select the folder of your SDK and click on `Select Folder` to open it up in Sublime Text. The folder will become visible in the bar on the left.
![open-project-image]()

### 3. Create Angular App File
Create an angular application where the logic of the project/app will go and save it in `scripts` folder (or according to the folder structure that the project is following). The rest of this document assumes that the angular app file is present in `scripts` folder.
> If your angular app files resides in a different folder/path, you will only need to replace the path references used in this document with the ones that are applicable in your project.

### 4. Create HTML file
Right click on the folder name and select the `New File` option to create a new test file. 
![open-new-file]()

Save it with an appropriate name such as `index.html`. Import the reference to the generated SDK files inside `index.html` like:
    ```html
    
    <!-- Helper files -->
    <script src="scripts/TesterLib/Configuration.js"></script>
    <script src="scripts/TesterLib/APIHelper.js"></script>
    <script src="scripts/TesterLib/Http/Client/HttpContext.js"></script>
    <script src="scripts/TesterLib/Http/Client/RequestClient.js"></script>
    <script src="scripts/TesterLib/Http/Request/HttpRequest.js"></script>
    <script src="scripts/TesterLib/Http/Response/HttpResponse.js"></script>

    <!-- API Controllers -->
    <script src="scripts/TesterLib/Controllers/ResponseTypesController.js"></script>
    <script src="scripts/TesterLib/Controllers/ErrorCodesController.js"></script>
    <script src="scripts/TesterLib/Controllers/BodyParamsController.js"></script>
    <script src="scripts/TesterLib/Controllers/FormParamsController.js"></script>
    <script src="scripts/TesterLib/Controllers/EchoController.js"></script>
    <script src="scripts/TesterLib/Controllers/HeaderController.js"></script>
    <script src="scripts/TesterLib/Controllers/QueryParamController.js"></script>
    <script src="scripts/TesterLib/Controllers/TemplateParamsController.js"></script>


    <!-- Models -->
    <script src="scripts/TesterLib/Models/ServerResponse.js"></script>
    <script src="scripts/TesterLib/Models/EchoResponse.js"></script>
    <script src="scripts/TesterLib/Models/QueryParameter.js"></script>
    <script src="scripts/TesterLib/Models/Person.js"></script>
    <script src="scripts/TesterLib/Models/Days.js"></script>
    <script src="scripts/TesterLib/Models/SuiteCode.js"></script>
    <script src="scripts/TesterLib/Models/Employee.js"></script>
    <script src="scripts/TesterLib/Models/GlobalTestException.js"></script>
    <script src="scripts/TesterLib/Models/LocalTestException.js"></script>

    ```
> The Configuration.js file should be imported before the other files.

### 5. Dependency Injection
In order to use the generated SDK's module, controllers and factories, they need to be added as a dependency in your project's module. 
Inject the SDK's module into your main module e.g:

    ```js
    var myApp = angular.module('myApp', ['TesterLib']);
    ```
To use a generated factory in your controller, injection could be as follows:

    ```js
    myApp.controller('appController', function($scope, ResponseTypesController) {
        ...
    }
    ```
### 6. Running The App
To run the app, simply open up the `index.html` file in a browser.
![app-running]()

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

The singleton instance of the ``` ResponseTypesController ``` class can be accessed via Dependency Injection.

```js
	app.controller("testController", function($scope, ResponseTypesController){
	});
```

#### <a name="get_long"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getLong") getLong

> TODO: Add a method description


```javascript
function getLong()
```

#### Example Usage

```javascript



	app.controller("testController", function($scope, ResponseTypesController){
		var result = ResponseTypesController.getLong();
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="get_model"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getModel") getModel

> TODO: Add a method description


```javascript
function getModel()
```

#### Example Usage

```javascript



	app.controller("testController", function($scope, ResponseTypesController){
		var result = ResponseTypesController.getModel();
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="get_string_enum_array"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getStringEnumArray") getStringEnumArray

> TODO: Add a method description


```javascript
function getStringEnumArray()
```

#### Example Usage

```javascript



	app.controller("testController", function($scope, ResponseTypesController){
		var result = ResponseTypesController.getStringEnumArray();
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="get_string_enum"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getStringEnum") getStringEnum

> TODO: Add a method description


```javascript
function getStringEnum()
```

#### Example Usage

```javascript



	app.controller("testController", function($scope, ResponseTypesController){
		var result = ResponseTypesController.getStringEnum();
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="get_model_array"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getModelArray") getModelArray

> TODO: Add a method description


```javascript
function getModelArray()
```

#### Example Usage

```javascript



	app.controller("testController", function($scope, ResponseTypesController){
		var result = ResponseTypesController.getModelArray();
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="get_int_enum"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getIntEnum") getIntEnum

> TODO: Add a method description


```javascript
function getIntEnum()
```

#### Example Usage

```javascript



	app.controller("testController", function($scope, ResponseTypesController){
		var result = ResponseTypesController.getIntEnum();
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="get_int_enum_array"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getIntEnumArray") getIntEnumArray

> TODO: Add a method description


```javascript
function getIntEnumArray()
```

#### Example Usage

```javascript



	app.controller("testController", function($scope, ResponseTypesController){
		var result = ResponseTypesController.getIntEnumArray();
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="get_precision"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getPrecision") getPrecision

> TODO: Add a method description


```javascript
function getPrecision()
```

#### Example Usage

```javascript



	app.controller("testController", function($scope, ResponseTypesController){
		var result = ResponseTypesController.getPrecision();
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="get_binary"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getBinary") getBinary

> gets a binary object


```javascript
function getBinary()
```

#### Example Usage

```javascript



	app.controller("testController", function($scope, ResponseTypesController){
		var result = ResponseTypesController.getBinary();
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="get_integer"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getInteger") getInteger

> Gets a integer response


```javascript
function getInteger()
```

#### Example Usage

```javascript



	app.controller("testController", function($scope, ResponseTypesController){
		var result = ResponseTypesController.getInteger();
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="get_integer_array"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getIntegerArray") getIntegerArray

> Get an array of integers.


```javascript
function getIntegerArray()
```

#### Example Usage

```javascript



	app.controller("testController", function($scope, ResponseTypesController){
		var result = ResponseTypesController.getIntegerArray();
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="get_dynamic"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getDynamic") getDynamic

> TODO: Add a method description


```javascript
function getDynamic()
```

#### Example Usage

```javascript



	app.controller("testController", function($scope, ResponseTypesController){
		var result = ResponseTypesController.getDynamic();
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="get_dynamic_array"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getDynamicArray") getDynamicArray

> TODO: Add a method description


```javascript
function getDynamicArray()
```

#### Example Usage

```javascript



	app.controller("testController", function($scope, ResponseTypesController){
		var result = ResponseTypesController.getDynamicArray();
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="get_datetime"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getDatetime") getDatetime

> TODO: Add a method description


```javascript
function getDatetime()
```

#### Example Usage

```javascript



	app.controller("testController", function($scope, ResponseTypesController){
		var result = ResponseTypesController.getDatetime();
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="get_datetime_array"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getDatetimeArray") getDatetimeArray

> TODO: Add a method description


```javascript
function getDatetimeArray()
```

#### Example Usage

```javascript



	app.controller("testController", function($scope, ResponseTypesController){
		var result = ResponseTypesController.getDatetimeArray();
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="get_boolean"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getBoolean") getBoolean

> TODO: Add a method description


```javascript
function getBoolean()
```

#### Example Usage

```javascript



	app.controller("testController", function($scope, ResponseTypesController){
		var result = ResponseTypesController.getBoolean();
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="get_boolean_array"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getBooleanArray") getBooleanArray

> TODO: Add a method description


```javascript
function getBooleanArray()
```

#### Example Usage

```javascript



	app.controller("testController", function($scope, ResponseTypesController){
		var result = ResponseTypesController.getBooleanArray();
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="get_headers"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getHeaders") getHeaders

> TODO: Add a method description


```javascript
function getHeaders()
```

#### Example Usage

```javascript



	app.controller("testController", function($scope, ResponseTypesController){
		var result = ResponseTypesController.getHeaders();
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



[Back to List of Controllers](#list_of_controllers)

### <a name="error_codes_controller"></a>![Class: ](http://apidocs.io/img/class.png ".ErrorCodesController") ErrorCodesController

#### Get singleton instance

The singleton instance of the ``` ErrorCodesController ``` class can be accessed via Dependency Injection.

```js
	app.controller("testController", function($scope, ErrorCodesController){
	});
```

#### <a name="get400"></a>![Method: ](http://apidocs.io/img/method.png ".ErrorCodesController.get400") get400

> TODO: Add a method description


```javascript
function get400()
```

#### Example Usage

```javascript



	app.controller("testController", function($scope, ErrorCodesController){
		var result = ErrorCodesController.get400();
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="get500"></a>![Method: ](http://apidocs.io/img/method.png ".ErrorCodesController.get500") get500

> TODO: Add a method description


```javascript
function get500()
```

#### Example Usage

```javascript



	app.controller("testController", function($scope, ErrorCodesController){
		var result = ErrorCodesController.get500();
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="get401"></a>![Method: ](http://apidocs.io/img/method.png ".ErrorCodesController.get401") get401

> TODO: Add a method description


```javascript
function get401()
```

#### Example Usage

```javascript



	app.controller("testController", function($scope, ErrorCodesController){
		var result = ErrorCodesController.get401();
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | 401 Local |




[Back to List of Controllers](#list_of_controllers)

### <a name="body_params_controller"></a>![Class: ](http://apidocs.io/img/class.png ".BodyParamsController") BodyParamsController

#### Get singleton instance

The singleton instance of the ``` BodyParamsController ``` class can be accessed via Dependency Injection.

```js
	app.controller("testController", function($scope, BodyParamsController){
	});
```

#### <a name="send_string_array"></a>![Method: ](http://apidocs.io/img/method.png ".BodyParamsController.sendStringArray") sendStringArray

> sends a string body param


```javascript
function sendStringArray(sarray)
```

#### Example Usage

```javascript

    var sarray = ["abc", "def"];


	app.controller("testController", function($scope, BodyParamsController){
		var result = BodyParamsController.sendStringArray(sarray);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="send_integer_array"></a>![Method: ](http://apidocs.io/img/method.png ".BodyParamsController.sendIntegerArray") sendIntegerArray

> TODO: Add a method description


```javascript
function sendIntegerArray(integers)
```

#### Example Usage

```javascript

    var integers = [1,2,3,4,5];


	app.controller("testController", function($scope, BodyParamsController){
		var result = BodyParamsController.sendIntegerArray(integers);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="send_model"></a>![Method: ](http://apidocs.io/img/method.png ".BodyParamsController.sendModel") sendModel

> TODO: Add a method description


```javascript
function sendModel(model)
```

#### Example Usage

```javascript

    var model = new Employee({"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]});


	app.controller("testController", function($scope, BodyParamsController){
		var result = BodyParamsController.sendModel(model);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="send_model_array"></a>![Method: ](http://apidocs.io/img/method.png ".BodyParamsController.sendModelArray") sendModelArray

> TODO: Add a method description


```javascript
function sendModelArray(models)
```

#### Example Usage

```javascript

    var models = [{"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]}, {"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]}].map(function(elem) {
        return new Employee(elem);
    });


	app.controller("testController", function($scope, BodyParamsController){
		var result = BodyParamsController.sendModelArray(models);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="send_dynamic"></a>![Method: ](http://apidocs.io/img/method.png ".BodyParamsController.sendDynamic") sendDynamic

> TODO: Add a method description


```javascript
function sendDynamic(dynamic)
```

#### Example Usage

```javascript

    var dynamic = {"uid": "1123213", "name": "Shahid"};


	app.controller("testController", function($scope, BodyParamsController){
		var result = BodyParamsController.sendDynamic(dynamic);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="send_string"></a>![Method: ](http://apidocs.io/img/method.png ".BodyParamsController.sendString") sendString

> TODO: Add a method description


```javascript
function sendString(value)
```

#### Example Usage

```javascript

    var value = "TestString";


	app.controller("testController", function($scope, BodyParamsController){
		var result = BodyParamsController.sendString(value);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="send_string_enum_array"></a>![Method: ](http://apidocs.io/img/method.png ".BodyParamsController.sendStringEnumArray") sendStringEnumArray

> TODO: Add a method description


```javascript
function sendStringEnumArray(days)
```

#### Example Usage

```javascript

    var days = ["Tuesday", "Saturday", "Wednesday", "Monday", "Sunday"];


	app.controller("testController", function($scope, BodyParamsController){
		var result = BodyParamsController.sendStringEnumArray(days);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="send_integer_enum_array"></a>![Method: ](http://apidocs.io/img/method.png ".BodyParamsController.sendIntegerEnumArray") sendIntegerEnumArray

> TODO: Add a method description


```javascript
function sendIntegerEnumArray(suites)
```

#### Example Usage

```javascript

    var suites = [1, 3, 4, 2, 3];


	app.controller("testController", function($scope, BodyParamsController){
		var result = BodyParamsController.sendIntegerEnumArray(suites);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



[Back to List of Controllers](#list_of_controllers)

### <a name="form_params_controller"></a>![Class: ](http://apidocs.io/img/class.png ".FormParamsController") FormParamsController

#### Get singleton instance

The singleton instance of the ``` FormParamsController ``` class can be accessed via Dependency Injection.

```js
	app.controller("testController", function($scope, FormParamsController){
	});
```

#### <a name="send_long"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendLong") sendLong

> TODO: Add a method description


```javascript
function sendLong(value)
```

#### Example Usage

```javascript

    var value = 5147483647;


	app.controller("testController", function($scope, FormParamsController){
		var result = FormParamsController.sendLong(value);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="send_integer_array"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendIntegerArray") sendIntegerArray

> TODO: Add a method description


```javascript
function sendIntegerArray(integers)
```

#### Example Usage

```javascript

    var integers = [1,2,3,4,5];


	app.controller("testController", function($scope, FormParamsController){
		var result = FormParamsController.sendIntegerArray(integers);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="send_string_array"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendStringArray") sendStringArray

> TODO: Add a method description


```javascript
function sendStringArray(strings)
```

#### Example Usage

```javascript

    var strings = ["abc", "def"];


	app.controller("testController", function($scope, FormParamsController){
		var result = FormParamsController.sendStringArray(strings);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="send_model"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendModel") sendModel

> TODO: Add a method description


```javascript
function sendModel(model)
```

#### Example Usage

```javascript

    var model = new Employee({"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]});


	app.controller("testController", function($scope, FormParamsController){
		var result = FormParamsController.sendModel(model);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="send_model_array"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendModelArray") sendModelArray

> TODO: Add a method description


```javascript
function sendModelArray(models)
```

#### Example Usage

```javascript

    var models = [{"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]}, {"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]}].map(function(elem) {
        return new Employee(elem);
    });


	app.controller("testController", function($scope, FormParamsController){
		var result = FormParamsController.sendModelArray(models);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="send_file"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendFile") sendFile

> TODO: Add a method description


```javascript
function sendFile(file)
```

#### Example Usage

```javascript

    var file = data;


	app.controller("testController", function($scope, FormParamsController){
		var result = FormParamsController.sendFile(file);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="send_mixed_array"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendMixedArray") sendMixedArray

> Send a variety for form params. Returns file count and body params


```javascript
function sendMixedArray(input)
```

#### Example Usage

```javascript

    var input = [];
        input["file"] = data;
        input["integers"] = [1,2,3,4,5];
        input["models"] = [{"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]}, {"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]}].map(function(elem) {
        return new Employee(elem);
    });
        input["strings"] = ["abc", "def"];


	app.controller("testController", function($scope, FormParamsController){
		var result = FormParamsController.sendMixedArray(input);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="send_string"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendString") sendString

> TODO: Add a method description


```javascript
function sendString(value)
```

#### Example Usage

```javascript

    var value = "TestString";


	app.controller("testController", function($scope, FormParamsController){
		var result = FormParamsController.sendString(value);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="send_integer_enum_array"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendIntegerEnumArray") sendIntegerEnumArray

> TODO: Add a method description


```javascript
function sendIntegerEnumArray(suites)
```

#### Example Usage

```javascript

    var suites = [1, 3, 4, 2, 3];


	app.controller("testController", function($scope, FormParamsController){
		var result = FormParamsController.sendIntegerEnumArray(suites);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="send_string_enum_array"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendStringEnumArray") sendStringEnumArray

> TODO: Add a method description


```javascript
function sendStringEnumArray(days)
```

#### Example Usage

```javascript

    var days = ["Tuesday", "Saturday", "Wednesday", "Monday", "Sunday"];


	app.controller("testController", function($scope, FormParamsController){
		var result = FormParamsController.sendStringEnumArray(days);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



[Back to List of Controllers](#list_of_controllers)

### <a name="echo_controller"></a>![Class: ](http://apidocs.io/img/class.png ".EchoController") EchoController

#### Get singleton instance

The singleton instance of the ``` EchoController ``` class can be accessed via Dependency Injection.

```js
	app.controller("testController", function($scope, EchoController){
	});
```

#### <a name="json_echo"></a>![Method: ](http://apidocs.io/img/method.png ".EchoController.jsonEcho") jsonEcho

> Echo's back the request


```javascript
function jsonEcho(input)
```

#### Example Usage

```javascript

    var input = {"uid": "1123213", "name": "Shahid"};


	app.controller("testController", function($scope, EchoController){
		var result = EchoController.jsonEcho(input);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="form_echo"></a>![Method: ](http://apidocs.io/img/method.png ".EchoController.formEcho") formEcho

> Sends the request including any form params as JSON


```javascript
function formEcho(input)
```

#### Example Usage

```javascript

    var input = {"uid": "1123213", "name": "Shahid"};


	app.controller("testController", function($scope, EchoController){
		var result = EchoController.formEcho(input);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="query_echo"></a>![Method: ](http://apidocs.io/img/method.png ".EchoController.queryEcho") queryEcho

> TODO: Add a method description


```javascript
function queryEcho(queryParameters)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| queryParameters | ``` Optional ``` | Additional optional query parameters are supported by this method |



#### Example Usage

```javascript


    // key-value map for optional query parameters
    var queryParameters = [];


	app.controller("testController", function($scope, EchoController){
		var result = EchoController.queryEcho(queryParameters);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



[Back to List of Controllers](#list_of_controllers)

### <a name="header_controller"></a>![Class: ](http://apidocs.io/img/class.png ".HeaderController") HeaderController

#### Get singleton instance

The singleton instance of the ``` HeaderController ``` class can be accessed via Dependency Injection.

```js
	app.controller("testController", function($scope, HeaderController){
	});
```

#### <a name="send_headers"></a>![Method: ](http://apidocs.io/img/method.png ".HeaderController.sendHeaders") sendHeaders

> Sends a single header params


```javascript
function sendHeaders(customHeader, value)
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


	app.controller("testController", function($scope, HeaderController){
		var result = HeaderController.sendHeaders(customHeader, value);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



[Back to List of Controllers](#list_of_controllers)

### <a name="query_param_controller"></a>![Class: ](http://apidocs.io/img/class.png ".QueryParamController") QueryParamController

#### Get singleton instance

The singleton instance of the ``` QueryParamController ``` class can be accessed via Dependency Injection.

```js
	app.controller("testController", function($scope, QueryParamController){
	});
```

#### <a name="simple_query"></a>![Method: ](http://apidocs.io/img/method.png ".QueryParamController.simpleQuery") simpleQuery

> TODO: Add a method description


```javascript
function simpleQuery(mboolean, number, string, queryParameters)
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
    var queryParameters = [];


	app.controller("testController", function($scope, QueryParamController){
		var result = QueryParamController.simpleQuery(mboolean, number, string, queryParameters);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="no_params"></a>![Method: ](http://apidocs.io/img/method.png ".QueryParamController.noParams") noParams

> TODO: Add a method description


```javascript
function noParams()
```

#### Example Usage

```javascript



	app.controller("testController", function($scope, QueryParamController){
		var result = QueryParamController.noParams();
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="string_param"></a>![Method: ](http://apidocs.io/img/method.png ".QueryParamController.stringParam") stringParam

> TODO: Add a method description


```javascript
function stringParam(string)
```

#### Example Usage

```javascript

    var string = "l;asd;asdwe[2304&&;'.d??\\a\\\\\\;sd//";


	app.controller("testController", function($scope, QueryParamController){
		var result = QueryParamController.stringParam(string);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="url_param"></a>![Method: ](http://apidocs.io/img/method.png ".QueryParamController.urlParam") urlParam

> TODO: Add a method description


```javascript
function urlParam(url)
```

#### Example Usage

```javascript

    var url = "https://www.shahidisawesome.com/and/also/a/narcissist?thisis=aparameter&another=one";


	app.controller("testController", function($scope, QueryParamController){
		var result = QueryParamController.urlParam(url);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="multiple_params"></a>![Method: ](http://apidocs.io/img/method.png ".QueryParamController.multipleParams") multipleParams

> TODO: Add a method description


```javascript
function multipleParams(number, precision, string, url)
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


	app.controller("testController", function($scope, QueryParamController){
		var result = QueryParamController.multipleParams(number, precision, string, url);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="number_array"></a>![Method: ](http://apidocs.io/img/method.png ".QueryParamController.numberArray") numberArray

> TODO: Add a method description


```javascript
function numberArray(integers)
```

#### Example Usage

```javascript

    var integers = [1,2,3,4,5];


	app.controller("testController", function($scope, QueryParamController){
		var result = QueryParamController.numberArray(integers);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="string_array"></a>![Method: ](http://apidocs.io/img/method.png ".QueryParamController.stringArray") stringArray

> TODO: Add a method description


```javascript
function stringArray(strings)
```

#### Example Usage

```javascript

    var strings = ["abc", "def"];


	app.controller("testController", function($scope, QueryParamController){
		var result = QueryParamController.stringArray(strings);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="string_enum_array"></a>![Method: ](http://apidocs.io/img/method.png ".QueryParamController.stringEnumArray") stringEnumArray

> TODO: Add a method description


```javascript
function stringEnumArray(days)
```

#### Example Usage

```javascript

    var days = ["Tuesday", "Saturday", "Wednesday", "Monday", "Sunday"];


	app.controller("testController", function($scope, QueryParamController){
		var result = QueryParamController.stringEnumArray(days);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="integer_enum_array"></a>![Method: ](http://apidocs.io/img/method.png ".QueryParamController.integerEnumArray") integerEnumArray

> TODO: Add a method description


```javascript
function integerEnumArray(suites)
```

#### Example Usage

```javascript

    var suites = [1, 3, 4, 2, 3];


	app.controller("testController", function($scope, QueryParamController){
		var result = QueryParamController.integerEnumArray(suites);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



[Back to List of Controllers](#list_of_controllers)

### <a name="template_params_controller"></a>![Class: ](http://apidocs.io/img/class.png ".TemplateParamsController") TemplateParamsController

#### Get singleton instance

The singleton instance of the ``` TemplateParamsController ``` class can be accessed via Dependency Injection.

```js
	app.controller("testController", function($scope, TemplateParamsController){
	});
```

#### <a name="send_string_array"></a>![Method: ](http://apidocs.io/img/method.png ".TemplateParamsController.sendStringArray") sendStringArray

> TODO: Add a method description


```javascript
function sendStringArray(strings)
```

#### Example Usage

```javascript

    var strings = ["abc", "def"];


	app.controller("testController", function($scope, TemplateParamsController){
		var result = TemplateParamsController.sendStringArray(strings);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



#### <a name="send_integer_array"></a>![Method: ](http://apidocs.io/img/method.png ".TemplateParamsController.sendIntegerArray") sendIntegerArray

> TODO: Add a method description


```javascript
function sendIntegerArray(integers)
```

#### Example Usage

```javascript

    var integers = [1,2,3,4,5];


	app.controller("testController", function($scope, TemplateParamsController){
		var result = TemplateParamsController.sendIntegerArray(integers);
        //Function call returns a promise
        result.then(function(resp){
			//success case
			console.log(resp.response);
			console.log(resp.body);
			//getting context of response
			console.log(resp.getContext());
		},function(err){
			//failure case
			console.log(err);
		});
	});
```



[Back to List of Controllers](#list_of_controllers)


