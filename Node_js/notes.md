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

