# Getting started

## How to Build

The generated SDK requires AngularJS framework to work. If you do not already have angular downloaded, please go ahead and do it from [here](https://angularjs.org/).
If any of your models have `Date` or `Datetime` type fields or your endpoints have `Date`/`Datetime` type response, you will need to download and link [angular-moment](https://cdnjs.cloudflare.com/ajax/libs/angular-moment/1.0.1/angular-moment.min.js) and [moment.js](https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.17.1/moment.min.js) with your project.

## How to Use

The following section describes how to use the generated SDK in an existing/new project.

### 1. Configure Angular and Generated SDK
Perform the following steps to configure angular and the SDK:
+ Make a `scripts` folder inside the root folder of the project. If you already have a `scripts` folder, skip to the next step.
+ Move the `angular.min.js` file inside the scripts folder. 
+ Move the `MarkdownNotesLib` folder inside the scripts folder.
+ If any of the Custom Types in your API have `Date`/`Datetime` type fields or any endpoint has `Date`/`Datetime` response, you will need to download angular-moment and moment.js. Move these 2 files into the `scripts` folder as well.

![folder-structure-image](https://apidocs.io/illustration/angularjs?step=folderStructure&workspaceFolder=Markdown%20Notes-Angular&projectName=MarkdownNotesLib)

### 2. Open Project Folder
Open an IDE/Text Editor for JavaScript like Sublime Text. The basic workflow presented here is also applicable if you prefer using a different editor or IDE.  
Click on `File` and select `Open Folder`

Select the folder of your SDK and click on `Select Folder` to open it up in Sublime Text. The folder will become visible in the bar on the left.

![open-folder-image](https://apidocs.io/illustration/angularjs?step=openFolder&workspaceFolder=Markdown%20Notes-Angular)

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

![initial-html-code-image](https://apidocs.io/illustration/angularjs?step=initialCode&workspaceFolder=Markdown%20Notes-Angular)

### 5. Including links to Angular in HTML file
Your HTML file needs to have a link to `angular.min.js` file to use Angular-JS. Add the link using `script` tags inside the `head` section of `index.html` like:
```html
<script src="scripts/angular.min.js" ></script>
```
If any of the Custom Types that you have defined have `Date`/`Datetime` type fields or any endpoint has `Date`/`Datetime` response, you will also need to link to angular-moment and moment.js like:
```html
<script src="scripts/angular.min.js" ></script>
<script src="scripts/moment.min.js" ></script>
<script src="scripts/angular-moment.min.js" ></script>
```

### 6. Include SDK references in HTML file
Import the reference to the generated SDK files inside your html file like:
```html
<head>
    ...
    <!-- Helper files -->
    <script src="scripts/MarkdownNotesLib/Module.js"></script>
    <script src="scripts/MarkdownNotesLib/Configuration.js"></script>
    <script src="scripts/MarkdownNotesLib/ModelFactory.js"></script>
    <script src="scripts/MarkdownNotesLib/ObjectMapper.js"></script>
    <script src="scripts/MarkdownNotesLib/APIHelper.js"></script>
    <script src="scripts/MarkdownNotesLib/Http/Client/HttpContext.js"></script>
    <script src="scripts/MarkdownNotesLib/Http/Client/RequestClient.js"></script>
    <script src="scripts/MarkdownNotesLib/Http/Request/HttpRequest.js"></script>
    <script src="scripts/MarkdownNotesLib/Http/Response/HttpResponse.js"></script>

    <!-- API Controllers -->
    <script src="scripts/MarkdownNotesLib/Controllers/BaseController.js"></script>
    <script src="scripts/MarkdownNotesLib/Controllers/UserController.js"></script>
    <script src="scripts/MarkdownNotesLib/Controllers/ServiceController.js"></script>
    <script src="scripts/MarkdownNotesLib/Controllers/NoteController.js"></script>


    <!-- Models -->
    <script src="scripts/MarkdownNotesLib/Models/BaseModel.js"></script>
    <script src="scripts/MarkdownNotesLib/Models/Note.js"></script>
    <script src="scripts/MarkdownNotesLib/Models/User.js"></script>
    <script src="scripts/MarkdownNotesLib/Models/ServiceStatus.js"></script>
    <script src="scripts/MarkdownNotesLib/Models/OAuthScopeEnum.js"></script>
    <script src="scripts/MarkdownNotesLib/Models/OAuthToken.js"></script>
    <script src="scripts/MarkdownNotesLib/Models/OAuthProviderErrorEnum.js"></script>

    ...
</head>
```
> The `Module.js` file should be imported before the other files. After `Module.js`, `Configuration.js` should be imported.
> The `ModelFactory.js` file is needed by `ObjectMapper.js` file. The `ObjectMapper` in turn, is needed by `BaseController.js`.

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
var app = angular.module('myApp', ['MarkdownNotesLib']);
```
At this point, the SDK has been successfully included in your project. Further steps include using a service/factory from the generated SDK. To see working example of this, please head on [over here](#list-of-controllers) and choose any class to see its functions and example usage.  

### 10. Running The App
To run the app, simply open up the `index.html` file in a browser.

![app-running](https://apidocs.io/illustration/angularjs?step=appRunning)

## Initialization


The Angular Application can be initialized as following:
```JavaScript
var app = angular.module('myApp', [MarkdownNotesLib]);
// now controllers/services can be created which import
// the factories provided by the sdk
```
### Authentication
In order to setup authentication and initialization of the Angular App, you need the following information.

| Parameter | Description |
|-----------|-------------|
| oAuthClientId | OAuth 2 Client ID |
| oAuthRedirectUri | OAuth 2 Redirection endpoint or Callback Uri |



```JavaScript
var app = angular.module('myApp', [MarkdownNotesLib]);
app.factory('config', function($scope, Configuration) 
{
    return {
        setConfigVars: function() {
            // Configuration parameters and credentials
            Configuration.oAuthClientId = 'oAuthClientId'; // OAuth 2 Client ID
            Configuration.oAuthRedirectUri = 'oAuthRedirectUri'; // OAuth 2 Redirection endpoint or Callback Uri
            
        }
    };
});
```


You must now authorize the client.

### Authorizing your client

Your application must obtain user authorization before it can execute an endpoint call. The SDK uses OAuth 2.0 Implicit Grant to obtain a user's consent to perform an API request on user's behalf.
The entire flow of building the authorization URL, obtaining consent from the user and storing the access token is handled by the SDK itself.


`retrieveAndSetAccessToken()` method will be called in order to obtain and set the access token in the `Configuration`.  You must pass the **[scopes](#scopes)** (for which you need permission to access) in this function.. Calling this method will open up the consent screen.  
Once the user responds to the consent request, the OAuth 2.0 server responds to your application's access request by redirecting the user to the redirect URI specified set in Configuration.

The redirect URI will receive the access token as the token argument in the URL fragment. This is how it will look

```
https://example.com/oauth/callback#token=XXXXXXXXXXXXXXXXXXXXXXXXX
```

The access token must be extracted by client-side JavaScript code.  
`OAuthCallbackScript.js` is the script which retrieves the access token and passes it as an event data to the window which actually opened up the consent screen (authorization url). You can simply link this with a html file to handle access token retrieval.

```html
<script src="OAuthCallbackScript.js"></script>
```




### Scopes

Scopes enable your application to only request access to the resources it needs while enabling users to control the amount of access they grant to your application. Available scopes are defined in the `MarkdownNotesLib/Models/OAuthScopeEnum` enumeration.

| Scope Name | Description |
| --- | --- |
| `READ_NOTE` | Can read all notes. |
| `WRITE_NOTE` | Can create, update and delete notes. |


### Complete Example

In order to set up the client side script which extracts the access token from the uri, perform the following steps:
Link the `OAuthCallbackScript.js` to the html file which is served at the registered redirect_uri for the application.
For example, if the redirect_uri is `http://localhost/callback.html`, create the `callback.html` in the root of the project folder. And add the following content:

#### `callback.html`

```html
<!DOCTYPE html>
<html>

<head>
    <title>OAuthTest</title>

</head>


<body>
    <script src="scripts/OAuthCallbackScript.js"></script>
</body>

</html>
```

This will ensure that the access token which will be received at `http://localhost/callback.html` will be retrieved by the `OAuthCallbackScript.js`.

After setting up as above, here's how the Implicit Grant flow can be executed.

#### `app.js`

```JavaScript
var app = angular.module('OAuthTest', ['MarkdownNotesLib']);

app.controller('oauthClientController', function($scope, OAuthManager, OAuthScopeEnum) {

    var scopes = [OAuthScopeEnum.READ_NOTE, OAuthScopeEnum.WRITE_NOTE];
    var promise = OAuthManager.retrieveAndSetAccessToken(scopes, '', true);
    promise.then(function(success) {
        // client successfully authorized
        // make endpoint calls as required
    });
});
```

#### `index.html`
```html
<!DOCTYPE html>
<html>

<head>
    <title>OAuthTest</title>
    <meta charset="UTF8">

    <script src="scripts/angular.min.js"></script>

    <script src="scripts/MarkdownNotesLib/Module.js"></script>
    <script src="scripts/MarkdownNotesLib/Configuration.js"></script>
    <script src="scripts/MarkdownNotesLib/ModelFactory.js"></script>
    <script src="scripts/MarkdownNotesLib/ObjectMapper.js"></script>
    <script src="scripts/MarkdownNotesLib/APIHelper.js"></script>
    <script src="scripts/MarkdownNotesLib/Servers.js"></script>
    <script src="scripts/MarkdownNotesLib/Environments.js"></script>
    <script src="scripts/MarkdownNotesLib/Http/Client/HttpContext.js"></script>
    <script src="scripts/MarkdownNotesLib/Http/Request/HttpRequest.js"></script>
    <script src="scripts/MarkdownNotesLib/Http/Response/HttpResponse.js"></script>
    <script src="scripts/MarkdownNotesLib/Http/Client/RequestClient.js"></script>

    // import controllers

    // import models

    <script src="scripts/MarkdownNotesLib/OAuthManager.js"></script>
    <script src="scripts/app.js"></script>

</head>


<body ng-app="OAuthTest">
    <div ng-controller="oauthClientController">

    </div>
</body>

</html>
```



# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [UserController](#user_controller)
* [ServiceController](#service_controller)
* [NoteController](#note_controller)

## <a name="user_controller"></a>![Class: ](https://apidocs.io/img/class.png ".UserController") UserController

### Get singleton instance

The singleton instance of the ``` UserController ``` class can be accessed via Dependency Injection.

```js
	app.controller("testController", function($scope, UserController, User){
	});
```

### <a name="get_user"></a>![Method: ](https://apidocs.io/img/method.png ".UserController.getUser") getUser

> TODO: Add a method description


```javascript
function getUser()
```

#### Example Usage

```javascript


	app.controller("testController", function($scope, UserController, User){


		var result = UserController.getUser();
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

## <a name="service_controller"></a>![Class: ](https://apidocs.io/img/class.png ".ServiceController") ServiceController

### Get singleton instance

The singleton instance of the ``` ServiceController ``` class can be accessed via Dependency Injection.

```js
	app.controller("testController", function($scope, ServiceController, ServiceStatus){
	});
```

### <a name="get_status"></a>![Method: ](https://apidocs.io/img/method.png ".ServiceController.getStatus") getStatus

> TODO: Add a method description


```javascript
function getStatus()
```

#### Example Usage

```javascript


	app.controller("testController", function($scope, ServiceController, ServiceStatus){


		var result = ServiceController.getStatus();
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

## <a name="note_controller"></a>![Class: ](https://apidocs.io/img/class.png ".NoteController") NoteController

### Get singleton instance

The singleton instance of the ``` NoteController ``` class can be accessed via Dependency Injection.

```js
	app.controller("testController", function($scope, NoteController, Note){
	});
```

### <a name="update_note"></a>![Method: ](https://apidocs.io/img/method.png ".NoteController.updateNote") updateNote

> TODO: Add a method description


```javascript
function updateNote(id, title, body)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| id |  ``` Required ```  | TODO: Add a parameter description |
| title |  ``` Required ```  | TODO: Add a parameter description |
| body |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, NoteController, Note){
        var id = 132;
        var title = 'title';
        var body = 'body';


		var result = NoteController.updateNote(id, title, body);
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



### <a name="delete_note"></a>![Method: ](https://apidocs.io/img/method.png ".NoteController.deleteNote") deleteNote

> TODO: Add a method description


```javascript
function deleteNote(id)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| id |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, NoteController){
        var id = 132;


		var result = NoteController.deleteNote(id);
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



### <a name="get_note"></a>![Method: ](https://apidocs.io/img/method.png ".NoteController.getNote") getNote

> TODO: Add a method description


```javascript
function getNote(id)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| id |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, NoteController, Note){
        var id = 132;


		var result = NoteController.getNote(id);
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



### <a name="create_note"></a>![Method: ](https://apidocs.io/img/method.png ".NoteController.createNote") createNote

> TODO: Add a method description


```javascript
function createNote(title, body)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| title |  ``` Required ```  | TODO: Add a parameter description |
| body |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript


	app.controller("testController", function($scope, NoteController, Note){
        var title = 'title';
        var body = 'body';


		var result = NoteController.createNote(title, body);
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



### <a name="list_notes"></a>![Method: ](https://apidocs.io/img/method.png ".NoteController.listNotes") listNotes

> TODO: Add a method description


```javascript
function listNotes()
```

#### Example Usage

```javascript


	app.controller("testController", function($scope, NoteController, Note){


		var result = NoteController.listNotes();
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



