# Node.js

## Roles and features of node.js

- Node.s is an open source, server-side javascript runtime built on Google's V8 engine, supporting Linux, Windows, and Mac OSX
- It is event-driven and uses asynchronous, non-blocking i/o, enabling efficient processing of web service requests.

### Difference between javascript and node.js

- Javascript is commonly used for client side scripting in browsers, while node.js allows javascript to run on the server side.
- Node.js handles server-side tasks such as processing HTTP request and routing, complementing client-side javascript.

## Express.js framework

- Express.js is a configurable framework that simplifies building Node.js application by abstracting lower-level APIs.
- It provides features like routing, middleware, template rendering, and static asset management, helping developers build applications quickly and efficiently.

### Modules and Module specifications

- A module is a file or collections of files containing related code serving a specific purpose.
- Module specification like CommonJS and ES modules define conventions for creating packages in Node.js
- Developers rely heavily on modules because of their reusability as well as their ability to break down complex code into manageable chunks
- Library owner can change the commonjs module into ES module by changing the extension(.js to .jsm)
- use them we have to export them first

### Import and require statements

- Module calling techniques into external applications
- **require** can be called anywhere in the code, support dynamic binding and is synchronous. it's used by commonjs, and errors are identified at runtime
- **import** must be called at the beginning of the file, uses static binding, and is asynchronous. it's used by ES, and errors are identified at compile time
- import is generally faster for large-scale application due to asynchronous loading.

### Purpose and roles of javascript

- Javascript is a widely used language for adding dynamic behavior to websites, originally running on the client side.
- It is an interpreted language, not requiring compilation, and can now run on servers embedded systems.

### Client-side vs Server-side javascript

- Client side javascript runs in the browser, handling user interface interactions and sending web service requests in JSON over HTTP.
- **Node.js**: with javascript process and routes these web services requests and routes web service requests on the server, running javascript code outside the browser.

### Node.js Framework

- Node.js is a server side framework that uses javascript to build scalable, concurrent server applications.
- It allows developers to quickly develop server applications with minimal tools, replacing traditional backend languages like java or php in handling web service requests.
- Every javascript file in node.js is treated as a module, and a package can contain one or more modules.
- HTTP.createServer function is used to create a web server instance, which can take a callback function to handle incoming HTTP requests and send responses and the server listens on specific port.

- **packages.json**: it includes fields like name, version, main script path, and license, which define the module's identity and usage.
- require is used to import node.js packages assuming .js file by default. when requiring directory, node.js looks for an index.js file as the default main script.
- Each module has an implicit export objects to which functions or values can be added to make them available externally.
- When modules are imported, the require returns  an object representing the module instance, allowing access to its exported properties.

### Types of modules in Node.js

- There are three modules: core, local and third party.
- **Core modules**: are built in module that provide essential functionality for developing node.js applications.
- **Local modules**: modules that are developed by the developers
_ **Third party**: are created by external developers and are typically available through package registries such as npm. These modules are distributed under different licenses, and developers should review licenses terms before use.

### Commonly used core modules

- *http, path, fs, os, util, url, and querystring*
- **http**: provides methods to transfer data over HTTP(to use it we require http module).
- Ex.

```bash
let http = require('http')
http.createServer(function (req, res){
    res.write('hello from server');
    res.end();
}).listen(6000)
```

- **fs**: is used to interact with files(i/o). it's part of the core node.js module
- EX.

```bash
    cont fs = require('fs');
    fs.readFile('sample.txt', 'utf8', (err, data) =>{
    if(err){
        console.error(err);
        return;
    }
    console.log(data);
    });
```

- **os**: used to retrieve information from the operating system that the application is running on and interact with it.

```bash
    let os = require = require('os');
    console.log("computer os platform info: " + os.platform());
    console.log("computer architecture info: " + os.arch());
```

- **path**: allows to retrieve and manipulate directory and file path.

```bash
    cont path = require('path');
    let result = path.basename('/content/index/home.html');
    console.log(result);
```

- **util**: is intended for internal use for accomplishing such tasks as debugging and deprecating functions.

```bash
let util = require('util');

let str = 'The loop has executed %d time(s).';

for (let i = 1; i <= 10; i++) {

	console.log(util.format(str, i)); //outputs 'The loop has executed i time(s)'

}
```

- **url**: used to divide up a web address into readable parts.

```bash
const url = require('url');

let webAddress = 'http://localhost:2000/index.html?lastName=Kent&firstName=Clark';

let qry = url.parse(webAddress, true);

let qrydata = qry.query; //returns an object: {lastName: 'Kent', firstName: 'Clark'}

console.log(qrydata.firstName); //outputs Clark


```

- **querystring**: provide methods to parse query strings from a url.

```bash
let qry = require('querystring');

let qryParams = qry.parse('lastName=Kent&firstName=Clark');

console.log(qryParams.firstName); //returns Clark
```

### Node package manager

- A package manager automates finding, installing, upgrading, configuring, and removing software packages and their dependencies.
- Dependencies are external code libraries or modules that a program relies on to function correctly.
- NPM serves an both command line interface(CLI) and online repository of javascript packages.
- It uses a package.json in the project root to track metadata and dependencies for a package(name, version, dependencies).

### Local and global installation with npm

- Local install place packages in the current project directory, making them accessible only to tha project.
- Global installs make the packages available to all applications on the machin but should be used carefully to avoid conflict.

### Asynchronous i/o and callback function

- **Asynchronous Network Operations**: in Node.js are non-blocking, meaning they return immediately without waiting for the operation to complete. This approach prevents wasting the application to continue running while waiting for network response.

### Callback function and HTTP request

- When making an HTTP request, Node.js immediately returns a result indicating the request was sent, not the response. A callback function is defined to handle the HTTP response once it arrives asynchronously from the remote server.

### Handling HTTP Responses in Node.js modules

- Custom Node.js modules can make HTTP requests and define callback functions to handle *data* and *end* events on the response. These callbacks process incoming data chunks and finalize the response handling , such as logging the response body.

## Callback Functions

- Callback Function Basics

    Node.js uses callback functions extensively to handle asynchronous operations, passing an error object as the first parameter.
    The callback function checks if an error exists; if so, it handles the error and cleans up resources; otherwise, it processes the successful result.

- Error Handling and Passing Results

    Callback functions pass error objects back to the main application to handle failures.
    When no error occurs, the callback is called with null as the first parameter and the result as the second.

- Linking Callbacks Between Modules and Applications

    Node.js modules make HTTP requests and define callback handlers for the HTTP response.
    To pass results from the module to the main application, one callback function calls another callback function provided by the main application.

- Example of Callback Usage

    The main application calls a module function and passes an anonymous callback to process results.
    The module calls http.request and, upon receiving the HTTP response, invokes the callback function that in turn calls the main application's callback with the result.

## Callback Issues

- Nested callback and callback hell
    Nested callback occur when multiple asynchronous tasks depends on each other and must be executed sequentially.
    This creates a callback hell or pyramid of doom structure, which reduces code readability and maintainability.
- Inversion of control issue
    IoC happens when the execution flow is controlled by third party code rather than you own.
    This can lead to difficulties in handling errors, timing issues, and unexpected behavior, requiring extra code to manage these risks.
- Mitigating call back problems
    Strategies to reduce callback hell and IoC issues include writing clear comments, breaking functions into smaller parts, and
    using modern js features like promises and async/await.

### Definition and states of Promises

- A promise is an object returned by an asynchronous method that represents the *eventual completion or failure* of an operation
- Promises have three states: *pending(initial state), resolved(operation resolved successfully) and rejected(operation failed).
- Usages:
    for handling time-consuming operations like API request and I/O operations.

### Handling HTTP Requests with Promises

- HTTP request can be blocking if done synchronously; Node.js packages like axios wrap HTTP requests in promises.
- The axios promise starts in a pending state, then resolves with a response or rejects with an error, handled using 'then' for success and 'catch' for errors.

### JSON

- Is the standard format for API data exchange and represents native js objects.
- json consists attribute-value pair
- json.parse() to convert json string into a js objects.
- json.stringify() to convert js object to json objects.

## Node.js and third party packages

### Extending Node.js with packages

* Node.js core features for building HTTP servers are limited; developers use external libraries for routing, authentication, database connection, and more.

* Parsing XML data manually with string functions is possible but inefficient and error-prone due to ignoring XML structures and potential data changes.

### Using xml2js package for XML parsing

- The xml2js Node.js packages converts XML strings into javascript objects, providing a structure and efficient  way to handle XML data.

- This package iss implemented purely in javascript and does not require external XML parsing libraries

> Node.js vs. Node Web Frameworks

    Node.js is a runtime environment that executes JavaScript on the server, not a web framework.
    Node web frameworks are built on top of Node.js to provide a structure for building web applications.

> Architectural Styles: MVC and REST API

    MVC (Model-View-Controller) divides an application into three parts: model (data management), view (data presentation), and controller (data flow control).
    REST APIs enable communication between web services using stateless HTTP methods like GET, POST, PATCH, and DELETE, often exchanging data in JSON format.

> Popular Node Web Frameworks

**Express.js**: A widely used framework for routing and middleware with a small learning curve and high performance.

**Koa**: A newer, smaller, and more expressive framework designed for complex, high-performance applications.

**Socket.io**: Ideal for real-time bidirectional communication, such as chat apps and multiplayer games.

**Hapi.js**: Known for security and built-in plugins, suitable for proxy servers and REST APIs.

**NestJS**: Built on Express, supports MVC, TypeScript, and combines object-oriented and reactive programming for scalable enterprise apps.

> Overview of Express Framework

    Express is a web application framework built on Node.js that abstracts low-level details to help organize and speed up application development.
    It supports middleware integration and handles various HTTP request methods, making it widely used and foundational for other frameworks.

> Primary Uses of Express

    Express is mainly used for building APIs, where it sets up HTTP interfaces to interact with data and sends JSON responses to clients.
    It is also used for server-side rendering (SSR), dynamically generating HTML, CSS, and JavaScript from templates to send back to the client browser.

> Installing and Setting Up Express

    The installation involves five steps: declaring Express as a dependency in the package.json file, running npm install to download modules, importing Express and creating an app, defining route handlers, and starting an HTTP server on a specified port.
    The package.json file includes metadata about the Node.js module and lists Express as a dependency with its version, while npm install ensures all required modules are downloaded into the node_modules directory.

> Installing and Setting Up Express

    Declare Express as a dependency in the package manifest (package.json) of your Node.js project.
    Run the npm command to download and install any missing modules required by Express.

> Creating the Express Application and Route Handler

    Import the Express module and create an instance of the Express application.
    Define a route handler that listens for HTTP GET requests on a specific resource path, capturing parameters from the URL.

> Starting the HTTP Server

    Use app.listen to start an HTTP server on a specified port number, enabling the application to listen for incoming requests.
    The server runs and responds to requests, such as retrieving current weather conditions based on a location parameter in the URL.

### Middleware and Messaging Frameworks

    Middleware is software that enables communication between applications, databases, or services, facilitating seamless interactions in distributed systems.
    Express is a messaging framework that handles routes and middleware, allowing the front end to communicate with back-end components without sharing the same language, often using JSON, REST APIs, or older protocols like XML and SOAP.

### Routes and Routing in Web Development

    A route links an HTTP request (GET, POST, DELETE, etc.) to a URL and the function that processes that request.
    Routing divides an application's user interface based on browser URL rules, with router functions collectively called middleware, which respond to requests or pass control along the middleware chain.

> Express Router Functions and Middleware Responsibilities

    Express uses the Router class with methods like Router.get(), Router.post(), Router.put(), and Router.delete() to handle HTTP requests, each taking a URL path and a callback function.
    Middleware also manages secure connections by encrypting/decrypting data, distributes application load across servers, and filters or sorts data before sending it back to the client.

### Routing in Express

    Routing handles different HTTP requests (GET, POST, PUT, DELETE) to various endpoints on the server.
    Routes can be managed at the application level or using routers for better organization when there are many endpoints.

> Middleware in Express

    Middleware functions have access to request, response, and next function to control the flow of request handling.
    Types of middleware include application-level, router-level, error-handling, built-in, and third-party middleware, each serving different purposes like authentication, error handling, or parsing requests.

> Template Rendering in Express

    Template rendering allows the server to generate dynamic HTML content by filling templates with data.
    Express can use view engines like express-react-views to render React components on the server side, enabling dynamic content display in web pages.

### Authentication Overview

    Authentication verifies a user's identity by validating credentials, ensuring only authorized users access certain system parts.
    The backend handles this verification process, which is crucial for application security.

### Session-Based Authentication

    Users log in with credentials validated against a database; a unique encrypted session ID is created and stored in both the database and browser cookie.
    The session ID is destroyed upon logout or after a timeout, ending the session.

### Token-Based Authentication and Authorization

    Authentication involves providing credentials to receive a token (often a JSON Web Token, JWT) that validates the user.
    Authorization uses the token to access resources, with tokens containing embedded permissions; JWTs have a header, payload (claims), and signature.

> Advantages of Token-Based Authentication

    Token-based authentication is scalable because tokens are stored on the client side, reducing server load.
    It offers flexibility by supporting multiple servers and diverse applications, with JWTs providing security through signing and encryption.

> Setting Up Authentication APIs

    A POST API endpoint allows users to log in by sending username and password, returning a signed JWT upon successful authentication.
    A GET API endpoint serves protected resources (employee information) and requires a valid token in the Authorization header to grant access.

> Implementation Details

    The Express server listens on port 5000 and initially restricts access to the protected endpoint with a 401 Unauthorized status.
    The "jsonwebtoken" package is used to generate and verify JWTs, with hardcoded credentials for demonstration (in practice, credentials and secrets should be securely managed).
    The GET API verifies the token from the Authorization header, granting access if valid or returning a 401 status if invalid or missing.


### Folder Structure for Express Applications

    Suggested directories include node_modules, config, models, routes, views, and public within the project folder.
    Key files include app.js (main configuration), routes.js (central route access), and package.json (dependency metadata).

> Folder Structure for Express APIs

    Similar to applications but excludes views and public folders.
    Includes node_modules, config, models, routes folders, and app.js, routes.js, package.json files.

> Best Practices for RESTful APIs

    Use nouns as resource identifiers in API routes.
    Correctly use HTTP status codes (200s for success, 300s for redirection, 400s for client errors, 500s for server errors).
    Perform black-box testing of APIs using tools like Mocha and SuperTest.
    Use JWT-based stateless authentication to maintain REST API statelessness.
    Provide proper API documentation using tools like API Blueprint or Swagger.

> Additional Tips for Express Development

    Use npm init to initialize projects and npm install with --save or --save-dev to manage dependencies.
    Avoid pushing node_modules to repositories.
    Follow naming conventions: lowercase for files, camelCase for variables, lowercase with dashes for npm modules, camelCase for require statements.
    Group similar routes into their own files and use config files for environment variables and credentials.

