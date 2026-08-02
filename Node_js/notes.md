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

