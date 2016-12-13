#Getting started

## How to Build

The generated SDK requires AngularJS framework to work. If you do not already have angular downloaded, please go ahead and do it from [here](https://angularjs.org/)

## How to Use

The following section describes how to use the generated SDK in an existing/new project.

### 1. Configure Angular and Generated SDK
Perform the following steps to configure angular and the SDK:
+ Make a `scripts` folder inside the root folder of the project. If you already have a `scripts` folder, skip to the next step.
+ Move the `angular.min.js` file inside the scripts folder. 
+ Move the `testerlib` folder inside the scripts folder.

![folder-structure-image](http://apidocs.io/illustration/angularjs?step=folderStructure&workspaceFolder=Tester-Angular&projectName=TesterLib)

### 2. Open Project Folder
Open an IDE/Text Editor for JavaScript like Sublime Text. The basic workflow presented here is also applicable if you prefer using a different editor or IDE.  
Click on `File` and select `Open Folder`

Select the folder of your SDK and click on `Select Folder` to open it up in Sublime Text. The folder will become visible in the bar on the left.

![open-folder-image](http://apidocs.io/illustration/angularjs?step=openFolder&workspaceFolder=Tester-Angular)

### 3. Create an Angular Application
Since Angular JS is used for client-side web development, in order to use the generated library, you will have to develop an application first.
If you already have an angular application, [skip to Step 6](#6-include-sdk-references-in-html-file). Otherwise, follow these steps to create one:

+ In the IDE, click on `File` and choose `New File` to create a new file.
+ Add the following starting code in the file:
```js
    var app = angular.module('myApp', []);
    app.controller('testController', function($scope) 
    {

    });
```
+ Save it with the name `app.js` in the `scripts` folder.


### 4. Create HTML File
Skip to the next step if you are working with an existing project and already have an html file. Otherwise follow the steps to create one:
+ Inside the IDE, right click on the project folder name and select the `New File` option to create a new test file.
+ Save it with an appropriate name such as `index.html` in the root of your project folder.
`index.html` should look like this:
```html
	<!DOCTYPE html>
	<html>
	<head>
		<title>Angular Project</title>
		<script></script>
	</head>

	<body>
	</body>

	</html>
```

![initial-html-code-image](http://apidocs.io/illustration/angularjs?step=initialCode&workspaceFolder=Tester-Angular)

### 5. Including links to Angular in HTML file
Your HTML file needs to have a link to `angular.min.js` file to use Angular-JS. Add the link using `script` tags inside the `head` section of `index.html` like:
```html
	<script src="scripts/angular.min.js" ></script>
```

### 6. Include SDK references in HTML file
Import the reference to the generated SDK files inside your html file like:
```html
	<head>
		...
		<!-- Helper files -->
		<script src="scripts/testerlib/Configuration.js"></script>
		<script src="scripts/testerlib/APIHelper.js"></script>
		<script src="scripts/testerlib/Http/Client/HttpContext.js"></script>
		<script src="scripts/testerlib/Http/Client/RequestClient.js"></script>
		<script src="scripts/testerlib/Http/Request/HttpRequest.js"></script>
		<script src="scripts/testerlib/Http/Response/HttpResponse.js"></script>

		<!-- API Controllers -->
        <script src="scripts/testerlib/Controllers/ResponseTypesController.js"></script>
        <script src="scripts/testerlib/Controllers/ErrorCodesController.js"></script>
        <script src="scripts/testerlib/Controllers/BodyParamsController.js"></script>
        <script src="scripts/testerlib/Controllers/FormParamsController.js"></script>
        <script src="scripts/testerlib/Controllers/EchoController.js"></script>
        <script src="scripts/testerlib/Controllers/HeaderController.js"></script>
        <script src="scripts/testerlib/Controllers/QueryParamController.js"></script>
        <script src="scripts/testerlib/Controllers/TemplateParamsController.js"></script>


		<!-- Models -->
        <script src="scripts/testerlib/Models/BaseModel.js"></script>
        <script src="scripts/testerlib/Models/ServerResponse.js"></script>
        <script src="scripts/testerlib/Models/EchoResponse.js"></script>
        <script src="scripts/testerlib/Models/QueryParameter.js"></script>
        <script src="scripts/testerlib/Models/Person.js"></script>
        <script src="scripts/testerlib/Models/Days.js"></script>
        <script src="scripts/testerlib/Models/SuiteCode.js"></script>
        <script src="scripts/testerlib/Models/Employee.js"></script>

		...
	</head>
```
> The Configuration.js file should be imported before the other files.

### 7. Including link to `app.js` in HTML file
Link your `app.js` file to your `index.html` file like:
```html
	<head>
		...
		<script src="scripts/app.js"></script>
	</head>
```
> The link to app.js needs to be included at the very end of the head tag, after the SDK references have been added

### 8. Initializing the Angular App
You need to initialize your app and the controller associated with your view inside your `index.html` file. Do so like:
+ Add ng-app directive to initialize your app inside the `body` tag.
```html
	<body ng-app="myApp">
```
+ Add ng-controller directive to initialize your controller and bind it with your view (`index.html` file).
```html
	...
	<body ng-app="myApp">
		<div ng-controller="testController">
			...
		</div>
		...
	</body>
	...
```

### 9. Consuming the SDK 
In order to use the generated SDK's modules, controllers and factories, the project needs to be added as a dependency in your angular app's module. This will be done inside the `app.js` file.
Add the dependency like this:

```js
    var app = angular.module('myApp', ['TesterLib']);
```
At this point, the SDK has been successfully included in your project. Further steps include using a service/factory from the generated SDK. To see working example of this, please head on [over here](#list-of-controllers) and choose any class to see its functions and example usage.  

### 10. Running The App
To run the app, simply open up the `index.html` file in a browser.

![app-running](http://apidocs.io/illustration/angularjs?step=appRunning)

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
	app.controller("testController", function($scope, ResponseTypesController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	});
```

#### <a name="get_long"></a>![Method: ](http://apidocs.io/img/method.png ".ResponseTypesController.getLong") getLong

> TODO: Add a method description


```javascript
function getLong()
```

#### Example Usage

```javascript


	app.controller("testController", function($scope, ResponseTypesController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	

		var result = ResponseTypesController.getLong();
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
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


	app.controller("testController", function($scope, ResponseTypesController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	

		var result = ResponseTypesController.getModel();
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
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


	app.controller("testController", function($scope, ResponseTypesController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	

		var result = ResponseTypesController.getStringEnumArray();
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
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


	app.controller("testController", function($scope, ResponseTypesController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	

		var result = ResponseTypesController.getStringEnum();
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
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


	app.controller("testController", function($scope, ResponseTypesController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	

		var result = ResponseTypesController.getModelArray();
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
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


	app.controller("testController", function($scope, ResponseTypesController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	

		var result = ResponseTypesController.getIntEnum();
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
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


	app.controller("testController", function($scope, ResponseTypesController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	

		var result = ResponseTypesController.getIntEnumArray();
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
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


	app.controller("testController", function($scope, ResponseTypesController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	

		var result = ResponseTypesController.getPrecision();
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
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


	app.controller("testController", function($scope, ResponseTypesController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	

		var result = ResponseTypesController.getBinary();
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
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


	app.controller("testController", function($scope, ResponseTypesController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	

		var result = ResponseTypesController.getInteger();
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
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


	app.controller("testController", function($scope, ResponseTypesController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	

		var result = ResponseTypesController.getIntegerArray();
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
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


	app.controller("testController", function($scope, ResponseTypesController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	

		var result = ResponseTypesController.getDynamic();
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
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


	app.controller("testController", function($scope, ResponseTypesController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	

		var result = ResponseTypesController.getDynamicArray();
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
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


	app.controller("testController", function($scope, ResponseTypesController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	

		var result = ResponseTypesController.getDatetime();
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
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


	app.controller("testController", function($scope, ResponseTypesController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	

		var result = ResponseTypesController.getDatetimeArray();
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
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


	app.controller("testController", function($scope, ResponseTypesController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	

		var result = ResponseTypesController.getBoolean();
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
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


	app.controller("testController", function($scope, ResponseTypesController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	

		var result = ResponseTypesController.getBooleanArray();
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
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


	app.controller("testController", function($scope, ResponseTypesController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	

		var result = ResponseTypesController.getHeaders();
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



[Back to List of Controllers](#list_of_controllers)

### <a name="error_codes_controller"></a>![Class: ](http://apidocs.io/img/class.png ".ErrorCodesController") ErrorCodesController

#### Get singleton instance

The singleton instance of the ``` ErrorCodesController ``` class can be accessed via Dependency Injection.

```js
	app.controller("testController", function($scope, ErrorCodesController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	});
```

#### <a name="get400"></a>![Method: ](http://apidocs.io/img/method.png ".ErrorCodesController.get400") get400

> TODO: Add a method description


```javascript
function get400()
```

#### Example Usage

```javascript


	app.controller("testController", function($scope, ErrorCodesController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	

		var result = ErrorCodesController.get400();
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
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


	app.controller("testController", function($scope, ErrorCodesController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	

		var result = ErrorCodesController.get500();
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
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


	app.controller("testController", function($scope, ErrorCodesController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	

		var result = ErrorCodesController.get401();
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
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
	app.controller("testController", function($scope, BodyParamsController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	});
```

#### <a name="send_string_array"></a>![Method: ](http://apidocs.io/img/method.png ".BodyParamsController.sendStringArray") sendStringArray

> sends a string body param


```javascript
function sendStringArray(sarray)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| sarray |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, BodyParamsController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var sarray = ["abc", "def"];


		var result = BodyParamsController.sendStringArray(sarray);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



#### <a name="send_integer_array"></a>![Method: ](http://apidocs.io/img/method.png ".BodyParamsController.sendIntegerArray") sendIntegerArray

> TODO: Add a method description


```javascript
function sendIntegerArray(integers)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| integers |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, BodyParamsController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var integers = [1,2,3,4,5];


		var result = BodyParamsController.sendIntegerArray(integers);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



#### <a name="send_model"></a>![Method: ](http://apidocs.io/img/method.png ".BodyParamsController.sendModel") sendModel

> TODO: Add a method description


```javascript
function sendModel(model)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| model |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, BodyParamsController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var model = new Employee({"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]});


		var result = BodyParamsController.sendModel(model);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



#### <a name="send_model_array"></a>![Method: ](http://apidocs.io/img/method.png ".BodyParamsController.sendModelArray") sendModelArray

> TODO: Add a method description


```javascript
function sendModelArray(models)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| models |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, BodyParamsController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var models = [{"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]}, {"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]}].map(function(elem) {
        return new Employee(elem);
    });


		var result = BodyParamsController.sendModelArray(models);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



#### <a name="send_dynamic"></a>![Method: ](http://apidocs.io/img/method.png ".BodyParamsController.sendDynamic") sendDynamic

> TODO: Add a method description


```javascript
function sendDynamic(dynamic)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| dynamic |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, BodyParamsController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var dynamic = {"uid": "1123213", "name": "Shahid"};


		var result = BodyParamsController.sendDynamic(dynamic);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



#### <a name="send_string"></a>![Method: ](http://apidocs.io/img/method.png ".BodyParamsController.sendString") sendString

> TODO: Add a method description


```javascript
function sendString(value)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| value |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, BodyParamsController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var value = "TestString";


		var result = BodyParamsController.sendString(value);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



#### <a name="send_string_enum_array"></a>![Method: ](http://apidocs.io/img/method.png ".BodyParamsController.sendStringEnumArray") sendStringEnumArray

> TODO: Add a method description


```javascript
function sendStringEnumArray(days)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| days |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, BodyParamsController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var days = ["Tuesday", "Saturday", "Wednesday", "Monday", "Sunday"];


		var result = BodyParamsController.sendStringEnumArray(days);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



#### <a name="send_integer_enum_array"></a>![Method: ](http://apidocs.io/img/method.png ".BodyParamsController.sendIntegerEnumArray") sendIntegerEnumArray

> TODO: Add a method description


```javascript
function sendIntegerEnumArray(suites)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| suites |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, BodyParamsController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var suites = [1, 3, 4, 2, 3];


		var result = BodyParamsController.sendIntegerEnumArray(suites);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



[Back to List of Controllers](#list_of_controllers)

### <a name="form_params_controller"></a>![Class: ](http://apidocs.io/img/class.png ".FormParamsController") FormParamsController

#### Get singleton instance

The singleton instance of the ``` FormParamsController ``` class can be accessed via Dependency Injection.

```js
	app.controller("testController", function($scope, FormParamsController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	});
```

#### <a name="send_long"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendLong") sendLong

> TODO: Add a method description


```javascript
function sendLong(value)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| value |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, FormParamsController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var value = 5147483647;


		var result = FormParamsController.sendLong(value);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



#### <a name="send_integer_array"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendIntegerArray") sendIntegerArray

> TODO: Add a method description


```javascript
function sendIntegerArray(integers)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| integers |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, FormParamsController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var integers = [1,2,3,4,5];


		var result = FormParamsController.sendIntegerArray(integers);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



#### <a name="send_string_array"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendStringArray") sendStringArray

> TODO: Add a method description


```javascript
function sendStringArray(strings)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| strings |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, FormParamsController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var strings = ["abc", "def"];


		var result = FormParamsController.sendStringArray(strings);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



#### <a name="send_model"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendModel") sendModel

> TODO: Add a method description


```javascript
function sendModel(model)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| model |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, FormParamsController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var model = new Employee({"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]});


		var result = FormParamsController.sendModel(model);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



#### <a name="send_model_array"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendModelArray") sendModelArray

> TODO: Add a method description


```javascript
function sendModelArray(models)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| models |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, FormParamsController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var models = [{"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]}, {"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]}].map(function(elem) {
        return new Employee(elem);
    });


		var result = FormParamsController.sendModelArray(models);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



#### <a name="send_file"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendFile") sendFile

> TODO: Add a method description


```javascript
function sendFile(file)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| file |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, FormParamsController, $http,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var file = data;


		$http.get("https://dl.dropboxusercontent.com/u/31838656/binary.png").then(function(successData){
            file = successData;
            var result = FormParamsController.sendFile(file);
        //Function call returns a promise
            result.then(function(success){
    			//success case
    			//getting context of response
    			console.log(success.getContext());
    		},function(err){
    			//failure case
    		});
    
    	}, function(errorData){
    
    	});
	});
```



#### <a name="send_mixed_array"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendMixedArray") sendMixedArray

> Send a variety for form params. Returns file count and body params


```javascript
function sendMixedArray(input)
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


	app.controller("testController", function($scope, FormParamsController, $http,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var input = [];
        input["file"] = data;
        input["integers"] = [1,2,3,4,5];
        input["models"] = [{"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]}, {"name":"Shahid Khaliq","age":5147483645,"address":"H # 531, S # 20","uid":"123321","salary":20000,"department":"Software Development","joiningDay":"Saturday","workingDays":["Monday","Tuesday","Friday"],"boss":{"name":"Zeeshan Ejaz","age":5147483647,"address":"I-9/1","uid":"241123"},"dependents":[{"name":"Future Wife","age":5147483649,"address":"H # 531, S # 20","uid":"123412"},{"name":"Future Kid","age":5147483648,"address":"H # 531, S # 20","uid":"312341"}]}].map(function(elem) {
        return new Employee(elem);
    });
        input["strings"] = ["abc", "def"];


		$http.get("https://dl.dropboxusercontent.com/u/31838656/binary.png").then(function(successData){
            input["file"] = successData;
            var result = FormParamsController.sendMixedArray(input);
        //Function call returns a promise
            result.then(function(success){
    			//success case
    			//getting context of response
    			console.log(success.getContext());
    		},function(err){
    			//failure case
    		});
    
    	}, function(errorData){
    
    	});
	});
```



#### <a name="send_string"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendString") sendString

> TODO: Add a method description


```javascript
function sendString(value)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| value |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, FormParamsController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var value = "TestString";


		var result = FormParamsController.sendString(value);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



#### <a name="send_integer_enum_array"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendIntegerEnumArray") sendIntegerEnumArray

> TODO: Add a method description


```javascript
function sendIntegerEnumArray(suites)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| suites |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, FormParamsController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var suites = [1, 3, 4, 2, 3];


		var result = FormParamsController.sendIntegerEnumArray(suites);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



#### <a name="send_string_enum_array"></a>![Method: ](http://apidocs.io/img/method.png ".FormParamsController.sendStringEnumArray") sendStringEnumArray

> TODO: Add a method description


```javascript
function sendStringEnumArray(days)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| days |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, FormParamsController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var days = ["Tuesday", "Saturday", "Wednesday", "Monday", "Sunday"];


		var result = FormParamsController.sendStringEnumArray(days);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



[Back to List of Controllers](#list_of_controllers)

### <a name="echo_controller"></a>![Class: ](http://apidocs.io/img/class.png ".EchoController") EchoController

#### Get singleton instance

The singleton instance of the ``` EchoController ``` class can be accessed via Dependency Injection.

```js
	app.controller("testController", function($scope, EchoController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	});
```

#### <a name="json_echo"></a>![Method: ](http://apidocs.io/img/method.png ".EchoController.jsonEcho") jsonEcho

> Echo's back the request


```javascript
function jsonEcho(input)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| input |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, EchoController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var input = {"uid": "1123213", "name": "Shahid"};


		var result = EchoController.jsonEcho(input);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



#### <a name="form_echo"></a>![Method: ](http://apidocs.io/img/method.png ".EchoController.formEcho") formEcho

> Sends the request including any form params as JSON


```javascript
function formEcho(input)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| input |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, EchoController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var input = {"uid": "1123213", "name": "Shahid"};


		var result = EchoController.formEcho(input);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
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


	app.controller("testController", function($scope, EchoController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	
        // key-value map for optional query parameters
        var queryParameters = [];


		var result = EchoController.queryEcho(queryParameters);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



[Back to List of Controllers](#list_of_controllers)

### <a name="header_controller"></a>![Class: ](http://apidocs.io/img/class.png ".HeaderController") HeaderController

#### Get singleton instance

The singleton instance of the ``` HeaderController ``` class can be accessed via Dependency Injection.

```js
	app.controller("testController", function($scope, HeaderController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
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


	app.controller("testController", function($scope, HeaderController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var customHeader = "TestString";
    var value = "TestString";


		var result = HeaderController.sendHeaders(customHeader, value);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



[Back to List of Controllers](#list_of_controllers)

### <a name="query_param_controller"></a>![Class: ](http://apidocs.io/img/class.png ".QueryParamController") QueryParamController

#### Get singleton instance

The singleton instance of the ``` QueryParamController ``` class can be accessed via Dependency Injection.

```js
	app.controller("testController", function($scope, QueryParamController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
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


	app.controller("testController", function($scope, QueryParamController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var mboolean = true;
    var number = 4;
    var string = "TestString";

        // key-value map for optional query parameters
        var queryParameters = [];


		var result = QueryParamController.simpleQuery(mboolean, number, string, queryParameters);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
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


	app.controller("testController", function($scope, QueryParamController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	

		var result = QueryParamController.noParams();
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



#### <a name="string_param"></a>![Method: ](http://apidocs.io/img/method.png ".QueryParamController.stringParam") stringParam

> TODO: Add a method description


```javascript
function stringParam(string)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| string |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, QueryParamController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var string = "l;asd;asdwe[2304&&;'.d??\\a\\\\\\;sd//";


		var result = QueryParamController.stringParam(string);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



#### <a name="url_param"></a>![Method: ](http://apidocs.io/img/method.png ".QueryParamController.urlParam") urlParam

> TODO: Add a method description


```javascript
function urlParam(url)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| url |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, QueryParamController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var url = "https://www.shahidisawesome.com/and/also/a/narcissist?thisis=aparameter&another=one";


		var result = QueryParamController.urlParam(url);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
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


	app.controller("testController", function($scope, QueryParamController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var number = 123412312;
    var precision = 1112.34;
    var string = "\"\"test./;\";12&&3asl\"\";\"qw1&34\"///..//.";
    var url = "http://www.abc.com/test?a=b&c=\"http://lolol.com?param=no&another=lol\"";


		var result = QueryParamController.multipleParams(number, precision, string, url);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



#### <a name="number_array"></a>![Method: ](http://apidocs.io/img/method.png ".QueryParamController.numberArray") numberArray

> TODO: Add a method description


```javascript
function numberArray(integers)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| integers |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, QueryParamController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var integers = [1,2,3,4,5];


		var result = QueryParamController.numberArray(integers);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



#### <a name="string_array"></a>![Method: ](http://apidocs.io/img/method.png ".QueryParamController.stringArray") stringArray

> TODO: Add a method description


```javascript
function stringArray(strings)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| strings |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, QueryParamController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var strings = ["abc", "def"];


		var result = QueryParamController.stringArray(strings);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



#### <a name="string_enum_array"></a>![Method: ](http://apidocs.io/img/method.png ".QueryParamController.stringEnumArray") stringEnumArray

> TODO: Add a method description


```javascript
function stringEnumArray(days)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| days |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, QueryParamController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var days = ["Tuesday", "Saturday", "Wednesday", "Monday", "Sunday"];


		var result = QueryParamController.stringEnumArray(days);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



#### <a name="integer_enum_array"></a>![Method: ](http://apidocs.io/img/method.png ".QueryParamController.integerEnumArray") integerEnumArray

> TODO: Add a method description


```javascript
function integerEnumArray(suites)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| suites |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, QueryParamController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var suites = [1, 3, 4, 2, 3];


		var result = QueryParamController.integerEnumArray(suites);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



[Back to List of Controllers](#list_of_controllers)

### <a name="template_params_controller"></a>![Class: ](http://apidocs.io/img/class.png ".TemplateParamsController") TemplateParamsController

#### Get singleton instance

The singleton instance of the ``` TemplateParamsController ``` class can be accessed via Dependency Injection.

```js
	app.controller("testController", function($scope, TemplateParamsController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	});
```

#### <a name="send_string_array"></a>![Method: ](http://apidocs.io/img/method.png ".TemplateParamsController.sendStringArray") sendStringArray

> TODO: Add a method description


```javascript
function sendStringArray(strings)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| strings |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, TemplateParamsController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var strings = ["abc", "def"];


		var result = TemplateParamsController.sendStringArray(strings);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



#### <a name="send_integer_array"></a>![Method: ](http://apidocs.io/img/method.png ".TemplateParamsController.sendIntegerArray") sendIntegerArray

> TODO: Add a method description


```javascript
function sendIntegerArray(integers)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| integers |  ``` Required ```  ``` Collection ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, TemplateParamsController,ServerResponse,EchoResponse,QueryParameter,Person,Days,SuiteCode,Employee){
	    var integers = [1,2,3,4,5];


		var result = TemplateParamsController.sendIntegerArray(integers);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```



[Back to List of Controllers](#list_of_controllers)



