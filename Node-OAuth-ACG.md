# 

## How to Build

The generated SDK relies on [Node Package Manager](https://www.npmjs.com/) (NPM) being available to resolve dependencies. If you don't already have NPM installed, please go ahead and follow instructions to install NPM from [here](https://nodejs.org/en/download/).
The SDK also requires Node to be installed. If Node isn't already installed, please install it from [here](https://nodejs.org/en/download/)
> NPM is installed by default when Node is installed

To check if node and npm have been successfully installed, write the following commands in command prompt:
* `node --version`
* `npm -version` 
![Version Check](https://apidocs.io/illustration/nodejs?step=versionCheck&workspaceFolder=Markdown%20Notes-Node)  

Now use npm to resolve all dependencies by running the following command in the root directory (of the SDK folder):
* `npm install`
![Resolve Dependencies](https://apidocs.io/illustration/nodejs?step=resolveDependency1&workspaceFolder=Markdown%20Notes-Node)
![Resolve Dependencies](https://apidocs.io/illustration/nodejs?step=resolveDependency2)

This will install all dependencies in the `node_modules` folder. 

Once dependencies are resolved, you will need to move the folder `MarkdownNotesLib ` in to your `node_modules` folder.

## How to Use

The following section explains how to use the library in a new project.

### 1. Open Project Folder
Open an IDE/Text Editor for JavaScript like Sublime Text. The basic workflow presented here is also applicable if you prefer using a different editor or IDE.  
Click on `File` and select `Open Folder`
![Open Folder](https://apidocs.io/illustration/nodejs?step=openFolder)

Select the folder of your SDK and click on `Select Folder` to open it up in Sublime Text. The folder will become visible in the bar on the left.
![Open Project](https://apidocs.io/illustration/nodejs?step=openProject&workspaceFolder=Markdown%20Notes-Node)


### 2. Creating a Test File
Now right click on the folder name and select the `New File` option to create a new test file.    Save it as `index.js` Now import the generated NodeJS library using the following lines of code:
```JavaScript
var lib = require('lib');
```
Save changes.

![Create new file](https://apidocs.io/illustration/nodejs?step=createNewFile&workspaceFolder=Markdown%20Notes-Node)
![Save new file](https://apidocs.io/illustration/nodejs?step=saveNewFile&workspaceFolder=Markdown%20Notes-Node)

### 3. Running The Test File
To run the `index.js` file, open up the command prompt and navigate to the Path where the SDK folder resides. Type the following command to run the file:  
`node index.js`
![Run file](https://apidocs.io/illustration/nodejs?step=runProject&workspaceFolder=Markdown%20Notes-Node)


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
2. Type `mocha  Markdown NotesController`  to run all the tests in that controller file.

> To increase mocha's default timeout, you can change the `TEST_TIMEOUT` parameter's value in `TestBootstrap.js`.  

![Run Tests](https://apidocs.io/illustration/nodejs?step=runTests&controllerName=Markdown%20NotesController)

## Initialization

### Authentication
In order to setup authentication in the API client, you need the following information.

| Parameter | Description |
|-----------|-------------|
| oAuthClientId | OAuth 2 Client ID |
| oAuthClientSecret | OAuth 2 Client Secret |
| oAuthRedirectUri | OAuth 2 Redirection endpoint or Callback Uri |



API client can be initialized as following:

```JavaScript
const lib = require('lib');

// Configuration parameters and credentials
lib.Configuration.oAuthClientId = "oAuthClientId"; // OAuth 2 Client ID
lib.Configuration.oAuthClientSecret = "oAuthClientSecret"; // OAuth 2 Client Secret
lib.Configuration.oAuthRedirectUri = "oAuthRedirectUri"; // OAuth 2 Redirection endpoint or Callback Uri

```

You must now authorize the client.

### Authorizing your client


Your application must obtain user authorization before it can execute an endpoint call. The SDK uses OAuth 2.0 authorization to obtain a user's consent to perform an API request on user's behalf.

#### 1. Obtaining user consent

To obtain user's consent, you must redirect the user to the authorization page. The `buildAuthorizationUrl()` method creates the URL to the authorization page. You must pass
the **[scopes](#scopes)** for which you need permission to access.
```JavaScript
const oAuthClient = lib.OAuthClient;
const authUrl = oAuthClient.buildAuthorizationUrl([OAuthScopeEnum.READ_NOTE, OAuthScopeEnum.WRITE_NOTE]);
// open up the authUrl in the browser
```

#### 2. Handle the OAuth server response

Once the user responds to the consent request, the OAuth 2.0 server responds to your application's access request by using the URL specified in the request.

If the user approves the request, the authorization code will be sent as the `code` query string:

```
https://example.com/oauth/callback?code=XXXXXXXXXXXXXXXXXXXXXXXXX
```

If the user does not approve the request, the response contains an `error` query string:

```
https://example.com/oauth/callback?error=access_denied
```

#### 3. Authorize the client using the code

After the server receives the code, it can exchange this for an *access token*. The access token is an object containing information for authorizing the client and refreshing the token itself.

```JavaScript
const tokenPromise = oAuthClient.authorize(code, additionalParams, callback);
```
The Node.js SDK supports both callbacks and promises. So, the authorize call returns a promise and also returns response back in the callback (if one is provided)



### Scopes

Scopes enable your application to only request access to the resources it needs while enabling users to control the amount of access they grant to your application. Available scopes are defined in the `lib/Models/OAuthScopeEnum` enumeration.

| Scope Name | Description |
| --- | --- |
| `READ_NOTE` | Can read all notes. |
| `WRITE_NOTE` | Can create, update and delete notes. |

### Refreshing token

Access tokens may expire after sometime. To extend its lifetime, you must refresh the token.

```JavaScript
const tokenExpiryPromise = oAuthClient.checkTokenExpiry();
// if token has expired, a rejected promise will be returned
tokenExpiryPromise.then(() => {}, () => {
    // token has expired
    const refreshPromise = oAuthClient.refreshToken();
    refreshPromise.then(() => {
        // token has been refreshed
    } , () => {
        // error occurred, handle exception
    });
});
```

If a token expires, the SDK will attempt to automatically refresh the token before the next endpoint call which requires authentication.


### Storing an access token for reuse

It is recommended that you store the access token for reuse.

You can store the access token in a variable.

```JavaScript
// store token
const token = lib.//Configuration.$oAuthToken.accessToken.accessToken;
```
However, since the the SDK will attempt to automatically refresh the token when it expires, it is recommended that you register a **token update callback** to detect any change to the access token.

```JavaScript
Configuration.oAuthTokenUpdateCallback = function() {
    // use a global variable or any other way to store the token
    _TOKEN = lib.//Configuration.$oAuthToken.accessToken.accesstoken;
}
```

The token update callback will be fired upon authorization as well as token refresh.

### Creating a client from a stored token

To authorize a client from a stored access token, just set the access token in `Configuration` along with the other configuration parameters before creating the client:

```JavaScript
// load token later...
const lib = require('lib');
lib.//Configuration.$oAuthToken = _TOKEN;
```
### Complete example

In this example, the `app.js` will first check if an access token is available for the user. If so, endpoint calls can be made as required. However, if the access token is not available, the client will have to be authorized first. For this purpose, the `server.js` file is used.  
The authorization url will be built and opened in the browser. Now the authorization code will be returned to the `redirect_uri`. In the `server.js` file, you will have to register a route with the same uri as the redirect_uri. Here the authorization code will be obtained and the client will be authorized. Endpoint calls can then be made.



#### `app.js`

```JavaScript
const lib = require('lib');
const oAuthClient = lib.OAuthClient;
lib.Configuration.oAuthClientId = 'oAuthClientId'; // OAuth 2 Client ID
lib.Configuration.oAuthClientSecret = 'oAuthClientSecret'; // OAuth 2 Client Secret
lib.Configuration.oAuthRedirectUri = 'http://localhost:1800/callback'; // OAuth 2 Redirection endpoint or Callback Uri

const isTokenSet = oAuthClient.checkTokenSet();
if (isTokenSet) {
    // make endpoint calls as required
} else {
    // since token is not set, client needs to obtain
    // an access token first
    const scopes = [];
    scopes.push([OAuthScopeEnum.READ_NOTE, OAuthScopeEnum.WRITE_NOTE]);
    const authUrl = oAuthClient.buildAuthorizationUrl(scopes);
    // open up the authUrl in the browser
}
```

#### `server.js`

```JavaScript
const lib = require('lib');
const oAuthClient = lib.OAuthClient;
const express = require('express');
const app = express();
const PORT = 1800;

app.listen(PORT, () => {
    console.log('Listening on port ' + PORT);
});

app.get('/callback', (req, res) => {
    const authCode = req.query.code;

    const promise = oAuthClient.authorize(authCode);
    promise.then((success) => {
        // client authorized, access token set
        // make endpoint calls as required
    });
});
```



# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [UserController](#user_controller)
* [ServiceController](#service_controller)
* [NoteController](#note_controller)
* [OAuthAuthorizationController](#o_auth_authorization_controller)

## <a name="user_controller"></a>![Class: ](https://apidocs.io/img/class.png ".UserController") UserController

### Get singleton instance

The singleton instance of the ``` UserController ``` class can be accessed from the API Client.

```javascript
var controller = lib.UserController;
```

### <a name="get_user"></a>![Method: ](https://apidocs.io/img/method.png ".UserController.getUser") getUser

> TODO: Add a method description


```javascript
function getUser(callback)
```

#### Example Usage

```javascript


    controller.getUser(function(error, response, context) {

    
	});
```



[Back to List of Controllers](#list_of_controllers)

## <a name="service_controller"></a>![Class: ](https://apidocs.io/img/class.png ".ServiceController") ServiceController

### Get singleton instance

The singleton instance of the ``` ServiceController ``` class can be accessed from the API Client.

```javascript
var controller = lib.ServiceController;
```

### <a name="get_status"></a>![Method: ](https://apidocs.io/img/method.png ".ServiceController.getStatus") getStatus

> TODO: Add a method description


```javascript
function getStatus(callback)
```

#### Example Usage

```javascript


    controller.getStatus(function(error, response, context) {

    
	});
```



[Back to List of Controllers](#list_of_controllers)

## <a name="note_controller"></a>![Class: ](https://apidocs.io/img/class.png ".NoteController") NoteController

### Get singleton instance

The singleton instance of the ``` NoteController ``` class can be accessed from the API Client.

```javascript
var controller = lib.NoteController;
```

### <a name="update_note"></a>![Method: ](https://apidocs.io/img/method.png ".NoteController.updateNote") updateNote

> TODO: Add a method description


```javascript
function updateNote(id, title, body, callback)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| id |  ``` Required ```  | TODO: Add a parameter description |
| title |  ``` Required ```  | TODO: Add a parameter description |
| body |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

    var id = 206;
    var title = 'title';
    var body = 'body';

    controller.updateNote(id, title, body, function(error, response, context) {

    
	});
```



### <a name="delete_note"></a>![Method: ](https://apidocs.io/img/method.png ".NoteController.deleteNote") deleteNote

> TODO: Add a method description


```javascript
function deleteNote(id, callback)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| id |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

    var id = 206;

    controller.deleteNote(id, function(error, response, context) {

    
	});
```



### <a name="get_note"></a>![Method: ](https://apidocs.io/img/method.png ".NoteController.getNote") getNote

> TODO: Add a method description


```javascript
function getNote(id, callback)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| id |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

    var id = 206;

    controller.getNote(id, function(error, response, context) {

    
	});
```



### <a name="create_note"></a>![Method: ](https://apidocs.io/img/method.png ".NoteController.createNote") createNote

> TODO: Add a method description


```javascript
function createNote(title, body, callback)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| title |  ``` Required ```  | TODO: Add a parameter description |
| body |  ``` Required ```  | TODO: Add a parameter description |



#### Example Usage

```javascript

    var title = 'title';
    var body = 'body';

    controller.createNote(title, body, function(error, response, context) {

    
	});
```



### <a name="list_notes"></a>![Method: ](https://apidocs.io/img/method.png ".NoteController.listNotes") listNotes

> TODO: Add a method description


```javascript
function listNotes(callback)
```

#### Example Usage

```javascript


    controller.listNotes(function(error, response, context) {

    
	});
```



[Back to List of Controllers](#list_of_controllers)

## <a name="o_auth_authorization_controller"></a>![Class: ](https://apidocs.io/img/class.png ".OAuthAuthorizationController") OAuthAuthorizationController

### Get singleton instance

The singleton instance of the ``` OAuthAuthorizationController ``` class can be accessed from the API Client.

```javascript
var controller = lib.OAuthAuthorizationController;
```

### <a name="request_token"></a>![Method: ](https://apidocs.io/img/method.png ".OAuthAuthorizationController.requestToken") requestToken

> *Tags:*  ``` Skips Authentication ``` 

> Create a new OAuth 2 token.


```javascript
function requestToken(authorization, code, redirectUri, formParams, callback)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| authorization |  ``` Required ```  | Authorization header in Basic auth format |
| code |  ``` Required ```  | Authorization Code |
| redirectUri |  ``` Required ```  | Redirect Uri |
| fieldParameters | ``` Optional ``` | Additional optional form parameters are supported by this method |



#### Example Usage

```javascript

    var authorization = 'Authorization';
    var code = 'code';
    var redirectUri = redirect_uri;
    // key-value map for optional form parameters
    var formParams = [];

    controller.requestToken(authorization, code, redirectUri, formParams, function(error, response, context) {

    
	});
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 400 | OAuth 2 provider returned an error. |
| 401 | OAuth 2 provider says client authentication failed. |




### <a name="refresh_token"></a>![Method: ](https://apidocs.io/img/method.png ".OAuthAuthorizationController.refreshToken") refreshToken

> *Tags:*  ``` Skips Authentication ``` 

> Obtain a new access token using a refresh token


```javascript
function refreshToken(authorization, refreshToken, scope, formParams, callback)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| authorization |  ``` Required ```  | Authorization header in Basic auth format |
| refreshToken |  ``` Required ```  | Refresh token |
| scope |  ``` Optional ```  | Requested scopes as a space-delimited list. |
| fieldParameters | ``` Optional ``` | Additional optional form parameters are supported by this method |



#### Example Usage

```javascript

    var authorization = 'Authorization';
    var refreshToken = refresh_token;
    var scope = 'scope';
    // key-value map for optional form parameters
    var formParams = [];

    controller.refreshToken(authorization, refreshToken, scope, formParams, function(error, response, context) {

    
	});
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 400 | OAuth 2 provider returned an error. |
| 401 | OAuth 2 provider says client authentication failed. |




[Back to List of Controllers](#list_of_controllers)



