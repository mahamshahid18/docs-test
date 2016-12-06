#Getting started

## How to Build

The generated SDK requires AngularJS framework to work. If you do not already have angular downloaded, please go ahead and do it from [here](https://angularjs.org/)

## How to Use

The following section describes how to use the generated SDK in an existing/new project.

### 1. Configure Angular and Generated SDK
Perform the following steps to configure angular and the SDK:
+ Make a `scripts` folder inside the root folder of the project. If you already have one, skip to the next step.
+ Move the `angular.min.js` file inside the scripts folder. 
+ Move the `calculatorlib` folder inside the scripts folder.
![folder-structure-image]()

### 2. Open Project Folder
Open an IDE/Text Editor for JavaScript like Sublime Text. The basic workflow presented here is also applicable if you prefer using a different editor or IDE.
Click on `File` and select `Open Folder`

Select the folder of your SDK and click on `Select Folder` to open it up in Sublime Text. The folder will become visible in the bar on the left.

### 3. Create an Angular Application
Since Angular JS is used for client-side web development, in order to use the generated library, you will have to develop an application first. To create a sample application, a tutorial listed [here](http://www.w3schools.com/angular/angular_application.asp) can be used as a reference. 

Follow the steps to create an angular application:
+ In the IDE, click on `File` and choose `New File` to create a new file.
+ Add the following starting code in the file:
```js
    var app = angular.module('myApp', []);
    app.controller('testController', function($scope) 
    {
        ...
    }
```
+ Save it with the name `app.js` in the root of the `scripts` folder.
 
> If you want to know how to include the generated SDK in the project, skip to [this](#5-including-generated-sdk-in-project)

### 4. Create HTML File
Right click on the folder name and select the `New File` option to create a new test file.

Save it with an appropriate name such as `index.html`. Import the reference to the generated SDK files inside `index.html` like:
```html
    <!-- Helper files -->
    <script src="scripts/CalculatorLib/Configuration.js"></script>
    <script src="scripts/CalculatorLib/APIHelper.js"></script>
    <script src="scripts/CalculatorLib/Http/Client/HttpContext.js"></script>
    <script src="scripts/CalculatorLib/Http/Client/RequestClient.js"></script>
    <script src="scripts/CalculatorLib/Http/Request/HttpRequest.js"></script>
    <script src="scripts/CalculatorLib/Http/Response/HttpResponse.js"></script>

    <!-- API Controllers -->
    <script src="scripts/CalculatorLib/Controllers/SimpleCalculatorController.js"></script>


    <!-- Models -->
    <script src="scripts/CalculatorLib/Models/BaseModel.js.js"></script>
    <script src="scripts/CalculatorLib/Models/Operation Type.js"></script>

```
> The Configuration.js file should be imported before the other files.

![example-html-code-image]()

### 5. Including Generated SDK in Project 
In order to use the generated SDK's modules, controllers and factories, they need to be added as a dependency in your project's module. 
Include the SDK's module into your main module e.g:

```js
    var app = angular.module('myApp', ['CalculatorLib']);
```
To use a generated factory/service in your controller, include it into the project as:

```js
    app.controller('testController', function($scope, SimpleCalculatorController) {
        ...
    }
```
![example-app-code-image]()

### 6. Running The App
To run the app, simply open up the `index.html` file in a browser.
![app-running]()

## Class Reference

### <a name="list_of_controllers"></a>List of Controllers

* [SimpleCalculatorController](#simple_calculator_controller)

### <a name="simple_calculator_controller"></a>![Class: ](http://apidocs.io/img/class.png ".SimpleCalculatorController") SimpleCalculatorController

#### Get singleton instance

The singleton instance of the ``` SimpleCalculatorController ``` class can be accessed via Dependency Injection.

```js
	app.controller("testController", function($scope, SimpleCalculatorController){
	});
```

#### <a name="get_calculate"></a>![Method: ](http://apidocs.io/img/method.png ".SimpleCalculatorController.getCalculate") getCalculate

> Calculates the expression based on the x and y operator


```javascript
function getCalculate(operation, x, y)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| operation |  ``` Required ```  | TODO: Add a parameter description |
| x |  ``` Required ```  | TODO: Add a parameter description |
| y |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

    var operation = Object.keys(Operation Type)[0];
    var x = 134.968504768316;
    var y = 134.968504768316;


	app.controller("testController", function($scope, SimpleCalculatorController){
		var result = SimpleCalculatorController.getCalculate(operation, x, y);
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



