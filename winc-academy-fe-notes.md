# FRONT-END DEVELOPMENT
##### Table of Contents (FE Modules)   
1. [HTML Basics](https://github.com/tomlajtos/winc-academy-notes/blob/main/winc-academy-fe-notes.md#html-basics--fe-module-1)      
2. [CSS Basics](https://github.com/tomlajtos/winc-academy-notes/blob/main/winc-academy-fe-notes.md#css-basics--fe-module-2)      
3. [JavaScript Basics](https://github.com/tomlajtos/winc-academy-notes/blob/main/winc-academy-fe-notes.md#javascript-basics--fe-module-3)      
4. [CSS Advanced](https://github.com/tomlajtos/winc-academy-notes/blob/main/winc-academy-fe-notes.md#css-advanced--fe-module-4)      
5. [Design and Accessibility](https://github.com/tomlajtos/winc-academy-notes/blob/main/winc-academy-fe-notes.md#design-and-accessibility--fe-module-5)   
6. [JavaScript Functions](https://github.com/tomlajtos/winc-academy-notes/blob/main/winc-academy-fe-notes.md#javascript-functions--fe-module-6)   
7. [JavaScript Advanced](https://github.com/tomlajtos/winc-academy-notes/blob/main/winc-academy-fe-notes.md#javascript-advanced--fe-module-7)   
8. [Professional Coding Setup](https://github.com/tomlajtos/winc-academy-notes/blob/main/winc-academy-fe-notes.md#professional-coding-setup--fe-module-8)   
9. [JavaScript in The Browser](https://github.com/tomlajtos/winc-academy-notes/blob/main/winc-academy-fe-notes.md#javascript-in-the-browser--fe-module-9)   
10. [Talking to The Backend](https://github.com/tomlajtos/winc-academy-notes/blob/main/winc-academy-fe-notes.md#talking-to-the--backend--api--basic-backend--fe-module-10)   
11. [React Basics](https://github.com/tomlajtos/winc-academy-notes/blob/main/winc-academy-fe-notes.md#ract-basics--fe-module-11)   
12. [React Advanced](#)   
---
## HTML Basics | FE Module 1
## CSS Basics | FE Module 2
## JavaScript Basics | FE Module 3
## CSS Advanced | FE Module 4
## Design and Accessibility | FE Module 5
## JavaScript Functions | FE Module 6
## JavaScript Advanced | FE Module 7
## Professional coding setup | FE Module 8
### 01. CLI (command line interface)
- ? > where am I - `pwd` (print working directory)
- ? > list - `ls/ ls -l/ -ls -la`
- ? > change directory - cd 'dirname' / cd ..
- ? > create directory - mkdir
- ? > delete directory - rmdir (only if it is empty) / rm -rf dir !!
- ? > create a file - touch 'filename'
- ? > remove a file - rm 'filename'
- ? >
- ? >

### 02. -
### 03. -
### 04. -
### 05. -

### 06. Node/npm
- install node/npm or NVM
- install nodemon (node monitor - live refresh on save in terminal)

### 07. Installing global npm packages
- ? > `npm install -g package_name`
- ? > run a package without installing it ==> use 'npx' i.e.: `npx package_name`
		(download __&rArr;__ run __&rArr;__ remove)
### 08. JavaScript projects
#### 08.01. Initialize a project with npm
- in project root __&rArr;__ `npm init` __&rArr;__ answer qs __&rArr;__ creates package.json (editable)

#### 08.02. Add script for nodemon
```javascript
{
"name": "zodiac_esm_solution",
"version": "1.0.0",
"description": "",
"main": "index.js",
"type": "commonjs", // or "module" if ES Module (ESM)
"scripts": { // define script here // ? >
"start": "nodemon --quiet"
},
"keywords": [],
"author": "",
"license": "ISC"
}
```
> ? > run the script: ./npm run start (runs nodemon in quiet mode)

#### 08.03 Splitting up a JavaScript project into modules
##### 08.03.01. CommonJS modules
- ? > export functions or variables with commonjs -- `modules.exports = { item1, item2, item2 };`
- ? > import from commonjs module -- `const {item1, item2, item3} = require("./moduleName");`

##### 08.03.02. ES Modules (ESM)
- ? > export functions or variables with ESM -- `export { item1, item2, item3 };`
- ? > import from ES module -- `import { item1, item2, item3 } from "./moduleName.js";`

##### 08.03.03. Using ESM and CommonJS in one project (ESM only is advised)
// !ONLY imports CommonJS modules into ES modules (doesn't work the other way)
- in package.json
	`"type": "module",`
- CommonJS module file extension is: fileName.cjs
- import statement in ESM needs to point to the full path of the module.cjs, extension included!
- tools to help with managing this: i.e. Babel

#### 08.04.  Package versions and scoped packages
##### 08.04.01. Semantic versioning:
> ? > Semantic version numbers look like this: 4.7.1 or 3.12.1 or 27.1.0.
- The 1st number indicates the MAJOR version.
- The 2nd number indicates the MINOR version.
- The 3rd number indicates the PATCH version.

##### 08.04.02. npm version calculator // [link](https://semver.npmjs.com/)
Query examples:
- '^2.1.3' __&rArr;__ any version with the same main version (1st no.) and minor and patch versions are equal or higher
- '~3.9.1' __&rArr;__ any verion within 3.9... patch number is equal or higher
- '>=4.1.0' __&rArr;__ any version that are equal or higher incl. major/minor/patch
- also based on the logic the following operators can be used too: >, <, <=
- 1.0.0 - 3.0.0 __&rArr;__ exact range, icluding the lover and upper limits

##### 08.04.03. Packages with a scope
@scope_name/package_name
- sometimes used by organizations - "@ibm/motion"
- or to group packages - i.e. "@storybook/"
	Advantage: easier naming of npm packages, any name can be used within a scope

#### 08.05. Third Party Dependencies
##### 08.05.01. Direct and Indirect Dependencies
- direct: where the project's code directly imports from / installed
- indirect (aka "transitive dependency"): package that is needed by another
	dependency __&rArr;__ dep. relations can be represented by a dep. tree.
- ? > TO SHOW DEPENDENCY TREE: "npm list -all"

##### 08.05.02. Development dependnecies ("dev dependencies")
- It is a dependency that is only needed during development. i.e.: formatter
- ? > Install a dev. dep. : `npm install -save-dev{package_name}` __&rArr;__ this will
	list the dep under the devDependencies in package.json

##### 08.05.03. Role of package.json and package-lock.json and differences
- ? > package.json: contains project metadata, configs and automation
- ? > package-lock.json: describe indeirect and direct dependencies down to the
		exact version number __&rArr;__ allows acurate rebuild without braking any code

##### 08.05.04. npm ci (clean install)
- to install a freshly downloaded project's dependencies
- best way with the command `npm ci` __&rArr;__ install dependencies from package-lock.json
	with the right version. [link](https://docs.npmjs.com/cli/v8/commands/npm-ci)

#### 08.06. Evaluating 3rd party code licensing
  conditions of oss/os project use is described in the project license (MIT etc.)

#### 08.07. Evaluating 3rd party code security
(aka "Software Supply Chain Security")
!!!__&rArr;__ npm packages have the risk potential to contain malwares, delete files or worse.
- npm install reports vulnerabilities
- use reliable source
- !!! wait with installig updates: couple days to see if there are problems
	EXCEPT: security updates
- npm audit: install package into an empty project and run 'npm audit' __&rArr;__ does a security scan [link](https://docs.npmjs.com/cli/v8/commands/npm-audit)
- use 3rd party security tools (i.e. Synk)

#### 08.08. Updating dependnecies
- on Github, use 'Dependabot' to track dependnecy updates automatically

### 09. Bundlers, buildtools and front-end toolchains
#### 09.01. Bundling code
- bundler will: analyze __&rArr;__ order __&rArr;__ sort __&rArr;__ combine the code __&rArr;__ send to browser
- Bundlers can also bundle non-JavaScript code like CSS
	* [Esbuild](https://esbuild.github.io/)
	* [Rollup](https://rollupjs.org/guide/en/)
	* [Webpack](https://webpack.js.org/)

#### 09.02. Compilatoin
  - converting code into output files (Sass >> CSS, TypeScript >> JS)

#### 09.03. Transpilation (source-to-source transpilation)
- rocess of taking code written using certain language constructs and converting it
	into code that does the same but uses different language construct
	i.e. ESM to CommonJS, or ES6 >> old JS for old browsers, Node >> browser

#### 09.04. Polyfilling (and code instead of transforming /like transpilation/)
- makes functionality available by adding code
	i.e. [js-temporal_polyfill](https://www.npmjs.com/package/@js-temporal/polyfill)

- XTRA-info: [link](https://javascript.info/polyfills)
- TOOLS for compilation and transpilation:
	* [Sass compiler](https://www.npmjs.com/package/sass)
	* [TypeScript compiler](https://www.npmjs.com/package/typescript)
	* [Babel](https://babeljs.io/)
	* [Webpack](https://webpack.js.org/)

#### 09.05. Image processing/optimization
- for website optimization (resize, crop) images need to be as light as possible
- Tools:
	* [imagemin package](https://github.com/imagemin/imagemin)

#### 09.06. Serving during development (dev server)
  - serv website and other project locally
  - some kind of live server application with HMR (hot module realoading)

#### 09.07. Ttoolchains
- combination of tools configured to work together
- e.i. by popularity:
	* [Vite](https://vitejs.dev/)
	* [Parcer](https://parceljs.org/)
	* [Rome](https://rome.tools/)
	* [WMR](https://wmr.dev/)

### 10. Version control
### 11. Version control bsics
- git
- web service to host repositories online: Github
	alt: Gitlab, Gitea

### 12. Git on the computer / local repo

## JavaScript in The Browser | FE Module 9

## Talking to The  Backend  (API & basic backend) | FE Module 10
### 01/02. Internet protocols: HTTP (HyperText Transort Protocol)
  [Internet Protocol Wikipedia](https://en.wikipedia.org/wiki/Internet_protocol_suite)

### 03. Request/Response
between client and server
type of HTTP requests we can send to a server:
- Get information from the server
-  Send new data to the server.
- Update existing data on the server.
- Delete data from the server. ==> CRUD (Create, Read, Update, Delete)

### 04. URL
Parts of a URL (required and optional):
- Scheme: i.e.: http, https, mailto, ftp etc.
- Host(or hostname): domain names, mapped to IP addresses
  (no necessary one-to-one relationship, multi dom can go to the same IP)
  i.e. www.google.com or, localhost:3000 (localhost is the host name)
    - www > subdomain, can be anything en.wikipedia.com ('en' is the sub.d)
    - google > domain name
    - .com > top-level domain
- Path: after the host/port or domain combination
  can be 0 or more segments:
  "www.google.../search/howsearchworks (2 segments)"
- User info: rare, i.e. "userName:secret"
- Port: usually only in local hosting, but the default for web is port 80
- Query: part after the '?', one or more key/value pairs separated by '&'
  used for simple filtering
  i.e. http://localhost?filter=true&country=us&state=california&city=losangeles
- Fragment: an optional part of the URL
  used to link to a specific part of the page

URLs in the backend
- a common structure pattern is the REST architecture
- resource: anithing that we may want to [C]reate [R]eade [U]pdate [D]elete
- each resource has its own URL, also often for types of resuorces (namespace, collection)
- URLs in this context called endpoints
Alternatives to REST: GraphQL, JSON: API
All backend structure uses HTTP

#### E: talk to different URLs - Postman
use restournat.json >> json-server >> endpoints: localhost:3000/menu, /tables, /reservations
- send GET request,
- modify url with item id,
- add filter queries: URL/endpoint?filterParam=value (num, string..)
- filter for value range URL/endpoint?filterParam_gte=value (num, string..) 'gte > greather than or equal to'

#### E: talk to different URLs - JavaScript
use restournat.json >> json-server >> endpoints: localhost:3000/menu, /tables, /reservations

### 05. Methods
- A request method is part of an HTTP request > 1 method/request
- Methods are allways written in uppercase letters
! the way a backend uses the methods can vary >> READ THE DOCS to know the exact way
[more info](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)

#### 05.01. GET (= read) & DELETE
- for retrieving (reading) data only
- can be sent to a namespace URL or a specific resource
- response is some data or an error if the backend does not now the request (> status codes)
In JS inside an `async` function >> i.e.:
```javascript
	const sendRequest = async() => {
		const response = await fetch("URL",{options_obj}); //*
		const json = await response.json();
		return json;
	};
```
* \*options_object: i.e.: `{method: "DELETE"}` >> `GET` if no options object

### 06. Status codes
- they tell us how the backend handeled a request
- it is a number between 100 & 599
- they also have a short name (for display, not in the code)
  i.e.: '200 OK' or '404 Not Found'
JS: use the status property of the response object   
```javascript
	const response = await fetch("http://localhost:3000/menu/5");
	console.log(response.status); //200
```

#### Most used statuscodes:
* 200 OK __&rArr;__ request handled successfuly
* 201 Created __&rArr;__ successful request,
* 401 Unauthorized __&rArr;__ request without or with wrong auth details
* 403 Forbidden __&rArr;__ system sending the request is not authorized to read the resource or perform the operation on it
* 404 Not Found __&rArr;__ esource the request was aiming at could not be found on the json-server
* 429 Too Many Requests __&rArr;__ too many requests from the same source
* 500 Internal Server Error __&rArr;__ backend has an unrecoverable problem while processing the request

### 07. Response body
#### 07.01. POST method
Postman >> in the response body (raw, JSON) include i.e.: a JSON object
```javascript
{
  "prop" : "val",
  "prop" : "val",
  "prop" : "val",
}
```
this will add a new object to the backend JSON file
(id is generated by the backend)
#### 07.02. PUT & PATCH method
Postman >> in the response body (raw, JSON) include i.e.: a JSON object
```javascript
{
  "prop" : "val",
  "prop" : "newVal",
  "prop" : "val",
}
```
this will replace the whole JSON object in the backend JSON file
The backend usually walidates the object in the PUT body

#### 07.03. POST, PUT and PATCH methods (JavaScript)
Opton obj for `fetch` should include:
- a body
- a specific header

* !Can't add a body to a GET with fetch (query params included in the query part of the URL)
FORMAT EXAMPLE:
```javascript
  fetch("URL", {
    method: "POST",
    body: '{"a":1}',
    headers: {
      "Content-Type":"application/json;charset=utf-8"
    }
  });
```
"POST" a new resource object will be created on the backend from the body
"PUT" the whole resource object will be replaced with the body
"PATCH" only whats included in the body will be changed, won't delete what is not in the body

### 08. Headers
- info about the messagei (message type, body type, message lifetime, authentication...),
- part of the message,
- both req. and res. can have headers
- std. header or custom header,
  [more info](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers)

#### 08.03. Request and Response headers
##### Request Header Examples:
- The Accept header (what content type the sender(client) accepts, single or multiple values
  `Accept: text/html`   
  `Accept: */*`   
  `Accept:   
  text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,    
  */*;q=0.8,application/signed-exchange;v=b3;q=0.9`   

- The Accept-Language header (client preffered human langs and locals)   
  `Accept-Language: de` for German, not specified to a country   
  `Accept-Language: nl-NL` for Dutch in the Netherlands   
  `Accept-Language: es_PE` for Peruvian Spanish   

- The Authorization header is used to send “credentials” to the server.   
  `Authorization: Basic taHDUsyEoZrxLTgkb7Ff`   
  `Authorization: Bearer CMn0QUmeH2miABK0d6qQ`   

- The Host header is a required and essential header.   
  contains the host and, optionally, the port the message is sent to   
  `Host: localhost:3000`   
  `Host: www.bbc.com`   
  `Host: en.wikipedia.org`   

- The User-Agent (or UA) header gives the receiver information about what kind of   
  system the sender is.   
  `User-Agent: Mozilla/5.0 (Windows NT 6.1; Win64; x64; rv:47.0) Gecko/20100101 Firefox/47.0`   
  `User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko)   
   Chrome/51.0.2704.103 Safari/537.36`   
  `User-Agent: Mozilla/5.0 (compatible; MSIE 9.0; Windows Phone OS 7.5; Trident/5.0;   
   IEMobile/9.0)`   

##### Rresponse Header Examples:
- The Content-Language Header   
  describes the language of the document   
  `Content-Language: pt-BR` for Brazilian Portuguese.   
  `Content-Language: en-CM` for English from the country Cameroon   
  `Content-Language: nl-BE` for Belgian Dutch   

##### Request and Rresponse Header Examples:
- The Cache-Control Header   
  contain instructions for the receiver on how to “cache” the content of the message   
  saving a received message locally so you don’t need to ask for it again which improves performance.   
  `Cache-Control: no-store`   
  `Cache-Control: public, max-age=86400`   
  `Cache-Control: public, min-fresh=3153600`   

- The Content-Langth Header   
  communicates the size of the message body in bytes   
  `Content-Length: 42`   
  `Content-Length: 544`   
  `Content-Length: 256808`   

- The Content Type Header   
  communicates the type of resource being sent   
  `Content-Type: text/html; charset=utf-8`   
  `Content-Type: text/css`   
  `Content-Type: image/png`   
  `Content-Type: application/json`   

- The Expires Header   
  communicates to the receiver when the response  will expire   
  `Expires: Wed, 21 Oct 2015 07:28:00 GMT`   
  `Expires: Thu, 2 Dec 2023 10:43:00 GMT`   
  `Expires: Mon, 17 Jan 2022 17:12:00 GMT`   

##### Exercise: inspect headers in browser devtools
- headers tab in network tab
- same for Postman __&rArr;__ add custom header {key:value}

#### 08.06. Exercise: inspect headers in JavaScript
- headers property of the response object is a headers object
- log all headers from response:
```javascript
const response = await fetch("http://localhost:3000");
for (const [header, value] of response.headers.entries()) {
	console.log(`${header}: ${value}`);
}
```
- check if a specific header exists(.has), check header value(.get):   
```javascript
const response = await fetch("http://localhost:3000/tables");
const headers = response.headers;
let contentType;
if (headers.has("content-type")) {
	contentType = headers.get("content-type");
}
console.log(contentType); //application/json: charset=utf-8
```
#### 08.07. Setting headers in fetch
- to set custom header in a request add headers prop to options object we pass to fetch   
```javascript
const url = "https://www.example.com"
const body = {a: 1};
const options = {};
options.method = "POST";
options.body = JSON.sringify(body);
options.headers = {
	Expires: "Thu, 2 Dec 2023 10:43:00 GMT",
	"Content-Type": "application/json;charset=utf-8",
};
fetch(url, options);
```
#### 08.08. Exercise: set headers in JavaScript
use syntax from above to add header to request body - inside options object for fetch()

### 09. Separating business logic from UI and IO
- better readability
- better maintainability   
	i.e. makes adding new logic easier, debugging easier etc.
- makes switching frameworks easier
- makes writing tests easier (separate test for IO, UI, b. logic)

### 10. Async / Await - Asynchronous JavaScript
- keep the program running while it is waiting for a server response
- if an async function returns a value we have to await that value... othervise  it is undefined.
i.e:   
```javascript
async function getData() { //asynchronous function declaration
	return 42;
}

const data = await getData(); // data is 42;
```

for server requestsi, the fetch method has to be wrapped in an async function,   
and the response has to be awaited. Also, each async function has to be awaited:   
```javascript
async function fetchData() {
	try {
		const response = await fetch('http://localhost:3000/todo');
		const todos = await response.json();
		console.table(todos);
	} catch (error) {
		console.error('no todos found');
	}
}
fetchData();
```

#### 10.04. Common Async Patterns
##### Pitfall of async code in JS:
- `await` blocks the code until it is resolved so awaiting at the top level of our code is not a good idea, it is better to await things when it is actually needed
- anything that depends on the result of await should be handled inside the async function itself. (with multiple, interdependent functions this can get complicated quickly __&rArr;__ everything is async)
  
##### Avoid having async functions everywhere:
__Inversion of control__:   
instead of caller function we let the async function handle the result from the asynchronous code. i.e.:     
```javascript
async function handleData() {
	const data = await fetchData();
	showData(data); // synchronous function, async spreading is stopped
}
```
It is important to contain async code!   

The sync and async code should be separated as much as possible. The rest of the code   
that has nothing to do with the async data should run independently. >> DO NOT await   
async code at the top level (EXECEPTION EXIST).   

All the awaiting happens inside the async function which is not awaited itself __&rArr;__ as soon it hits an await the the control flow is handeled back to wherever the      
async function was called __&rArr;__ rest of the code continues to execute (concept - EVENT LOOP)   

##### Successive async function calls (async code depends on other async code)
i.e.: make request based on prev requested data   
```javascript
async function handlePosts() {
	const user = await fetchUser();
	cosnt posts = await fetchPosts(user.id);
	showPosts(posts); // regular sync function
}
```

##### Multiple independent async code __&rArr;__ paralel requests >> do not await them in succession
i.e.:   
```javascript
async function handlePosts() {
	const asyncFriends = fetchFriends(); // no await
	cosnt asyncPosts = fetchPosts(user.id); // no await
	// both requests have been fired

	// await the posts
	showPosts(await asyncPosts);
	// await friends
	showFriends(await asyncFriends);
}
```
The fetche's result (a promise) is stored in a constant.      
We do not have to immediately await an async function in order to get the data out of it.      
We can keep a reference to the Promise and await it later on   

##### Different requests can take different time (some times big diff)   
- each requests should be handled as the result comes in
- wrap them individually an async function
- call them independently and handle them in the order they come in

```javascript
async function handleRequests() {
	async function hadleFriends() {
	const friends = await fetchFriends();
	showFriends(friends);
	}

	async function handlePosts() {
	const posts = await fetchPosts();
	showPosts(posts);
	}

	await Promise.all([ // takes an array of promisses and resolvs when all of them are resolved
	handlePosts(),    // returns a single promise, aggregating the results of multiple promisses __&rArr;__ used with relaterd promisses
	handleFriends(),
	]);
}
```
[more about Promise.all](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/all)

##### Top level await
It is possible to awati at the top level of a JS module, __HOWEVER__:   
- a module with top level await will be awaited by other modules when they import it so it sort of blocks the execution (other imported synchronous modules will run tho)
__!!!Only use top level await in modules that are strictly used for fetching some data and exporting it, and never place synchronous code after your asynchronous code when using top-level await (unless you need the result of the asynchronous code).__   

EXTRA RESOURCES for async/await:   
- [Async function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
- [Await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/await)

### 11. Promises
(async/await is built on top of promises)   
- Promise: a special type of object that holds a future value  (not yet now at that point in the code execution)

Async/Await is preferred ower Promises => more modern, promises are used in older codebases, libraries   

The different state of promises:   
- pending : at the time when it is created
- fulfilled
- rejected

They can be created in multiple ways:   
- using 'fetch' > fetch automatically returns a promise
- each async function returns a promise
- they are object with methods and we can create them ourselves by using the 'new' keyword (but this is increasingly rare, mostly done in library code)

```javascript
const amILucky = new Promise((resolve, reject) => {
	if (Math.random() < 0.99) {
		reject(new Error('You ain't lucky'));
	}
	resolve('You're lucky!);
});
```
there is a specific way to define what happens when a p. is fulfilled or rejected:   
1. .then() method __&rArr;__ takes the Promise value as its argument   
	 ```javascript
	 amILucky.then((fulfilledValue) => console.log(fulfilledValue));
	 ```
2. handling errors can be done in two ways: using .then() or using .catch():   
	 ```javascript
	 amILucky
		.then((fulfilledValue) => console.log(fulfilledValue));
		.catch((error) => console.log('some message', error));
	 ```
#### Chaining Promises
both .then() and .catch() return new promises > so we can chain several of them together   
This allows for complex code i.e. performing several requests in succession.   

```javascript
fetch('http://localhost:3000/todo')
	.then(response => response.json())
	.then(todos => console.table(todos))
	.catch(error => console.error('no todos found!'));
```

[Promises - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)   
[Using Promises - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises)   

### 12. Event Loop
- The event loop is a loop where the code can be scheduled
- The most simple example is the setTimeout() function > schedules code, code runs after set time, time unit is ms.
```javascript
setTimeout(() => {
	alert('at least 1 second has passed');
}, 1000);
```
- but also there are requestAnimationTimeframe and micro tasks which get executed in different times in relation to the browser page-rendering
and their execution also depends on the state of the JS callstack. >> can get complicated and lead to unexpected rendering

[YT vid - Jake Archibald](https://www.youtube.com/watch?v=cCOL7MC4Pl0)   
[MDN - event loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/EventLoop)   

### 13. Render API response in DOM
![figure application (fe &harr; be)](./winc-fe-notes-figures/application.png)   

__good place to start where the least connections & interdependencies are between the diff parts__   
- not a lot of other code is needed for this part and testing is easier too
- from the diagram these are: IO for sending or retrievieng, UI part where we render HTML based on data

__or places/features that are close to user interaction__   
- i.e.: code that listens to and processes events, easy testing, easy to see if we input the right data
- diagram: user interaction part

__start with the "happy path", scenario when everithing works with realistic input__   
- start with the easy part
- dont worry about edge cases and diff errors

When all that is done, focus on code for when things go wrong:   
- validating user input
- showing validation results
- handling errors and displaying error messages correctly

Happy path in the diagram: app logic/business rules w/o validation, IO without catching errors   

! check if th code is woring before and after adding new features to it   

? END DETOUR ?   

#### Exercise: API response rendering

## Ract Basics | FE module 11
[documentation](https://react.dev/)
### Introduction 
#### Benefits:
- less code more functionality compared to JS only approach
- rel. easy: combines JS and HTML concepts
- reusable: uses components as main building blocks for applications
- performance: uses virtual DOM, compares changes in the app and updates those changes in the real DOM (instead of updating all components)
- possibility of creating both web and mobile (React native framework) apps
- good debugging tools (React Dev Tools in Chrome)

NOTE: it ships a lot of JS so loading time could be slow   
SOLUTION: code splitting > only code that is needed will load sever side rendering > sends a fully rendered page as a static HTML markup   

#### Features:
React adds a layer of abstraction over using JS directly on the DOM   
- Components:   
UI components are the building blocks of a bigger UI >> easy debug, re-use of component in multi page apps   

- Props:   
using properties we can pass functions and data to other components >> dinamic/interacting components   

- State:   
keep track of values by storing them in a "state" object   

- JSX:   
components use JSX (JS XML) which is an extension to JS - combines parts of HTML and JS   

- Virtual DOM:   
higher version of DOM - it can be uploaded independently of the real DOM   
it is not able to make changes on the screen (it has all the props as the real DOM however)   

if change in React __&rArr;__ new version of V-DOM __&rArr;__ periodically compared to the real DOM and updates whenever    
there is a diff === RECONCILIATION   

#### Other frameworks:
- Angular (old but receiving major improvements lately
- Vue
- Backbone
- Ember 
etc.   

#### Drawbacks in React:
- documentation is less beginner friendly and not very structured
- requires a lot of planning (because of its flexibility)
- state management is not perfect

[Angular](https://www.ava.codes/posts/react-alternatives#toc-angular-a-stable-framework-based-on-typescript)   
[Vue](https://www.ava.codes/posts/react-alternatives#toc-vue-js-a-framework-for-fast-ui-building)

### 01. Setup
#### Steps
1. `pnpm create vite@latest my-first-app --template react`
2. `cd my-first-app` >> `npm install` => installs dependencies
3. edit Vite config 
4. `pnpm rund dev` => runs the app via __Vite__-server
5. `pnpm eslint --init` => set up Eslint
6. edit `eslintrc` >> 

	```javascript
	"rules": {
		"react/prop-types":0
	}
	```

7. `src/App.js` is the file that's running a code at --localhost 

#### Files and Directories, Organize a project:
can be done based on <u>types</u>, features, pages, etc.   

- create a `components` folder inside `src` (for reusable comps) 
	/some comps have child-parent realationship - these can be grouped in a folder inside `components`
- all generic UI comps will be grouped in a `ui` folder
- `pages` folder for page files, can add sub-folders for pages storing the page components, 1xuse comps

<img src="./winc-fe-notes-figures/react-project-str.jpg" title="React project file structure" alt="Basic React project structure" width="50%" height="50%"/>

#### Importing and Exporting files
[MDN documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules)   

Ways to use import in React:   
1. import a default export
```javascript
export default App;
//////////////////////////////
import App from "./App";
```
2. when export is not a default exp. << __RECOMMENDED__   
```javascript
export const App = () => {...};
//////////////////////////////
import {App} from "./App"
```
To import multiple modules:   
`import React, {useState} from 'react';`

### 02. JSX (JavaScript XML)
It is a combination of JS and HTML   
Allows for an easier DOM manipulation, but with an extra layer of abstraction,       
it is transformed into JS and HTML which the browser can understand       
Example code of a simple component:   
```javascript
import './App.css';

function App() {
	const greeting = "Hi, this is an app made with React"; // variables defined outside the `return()`
	const description = <p>I think it holds an interestig future</p>;

	return (
		<div className="App">
			<h1> Welcome! </h1>
			<p>{greeting}</p> // variable is a string which will be the content within the `<p>` tags
			{description} // tags saved in the variable, injecting the variable here without any tags
		</div>
	);
}

export default App;
```

JSX code goes inside `return ()`   

### 03. Rendering Components
#### Rendering
React uses a render function that takes two arguments: HTML code and an HTML element.      

It is to display HTML code inside the specified HTML element. I.e.: (from my-first-app/src/main.jsx)      
```javascript
ReactDOM.createRoot(document.getElementById('root')).render(  // define root DOM node
	<React.StrictMode>
		<App />
	</React.StrictMode>,
);
```
- everything inside root is handled by React (almost always a single root DOM node / React app)   
- `render()` __&rArr;__ to render a React element:   
	* pass the root DOM element (`document.getElementById('root')` to `ReactDOM.createRoot()`
	* then use the __render function__ on this root element   
- the React DOM uses a Virtual DOM   
	* the V-DOM is a lighter, in memory version of the DOM
	* can be updated without effecting the DOM
	* contains the sam properties, but it can't make changes on the screen   
	* React detects the elements that were changed and updates the DOM (uncanged DOM elements will not render again)
  > change in React __&rArr;__ V-DOM render __&rArr;__ React compares V-DOM and DOM periodically __&rArr;__ when diff. DOM is updated (reconciliation process)   

#### Components
A React app consists of many different components.     
These can be reused if needed.   

Components can be defined as <u>__functions__</u> (easier to use and maintain) or __classes__.  

Example for a __React Function Component__:   
```javascript
import './App.css';  // import styles

export const App = () => {  // export App component
	const hello = "Hello Wincer!"; 

  return (  // return JSX
		<main>
			<h1>{hello}</h1> // inject JS code by wrapping the variable name in {}, the value will render as an <h1>
		</main>
	);
};
```

It is possible to render a component inside another component
```javascript
import './App.css';

const Button = () => {  // define a Button component within the same file (can also be imported, !name is capitalized by conv.
	return (
		<button className="Button">Press me!</button>  // note: className (because 'class' is a reserved word in JS)
	);
};

export const App = () => {
  const hello = "Hello Wincer!";

	return (
		<main>
			<h1>{hello}</h1>
			<Button />  // to use inside "App", wrap "Button" in < /> when adding it to the JSX code, note: capitalized name to ditinguish from <button>
		</main>
	);
};
```

#### Fragment
__! in React only one element can be returned from a component__   
SOLUTION: wrap components in a container such as `<div>` or in a __React Fragment__   
Fragment syntax: `<React.Fragment>...</React.Fragment>` or `<>...</>`   
Example:
```javascript
export const App = () => {
	return (
    <>
      <Header />
      <Footer />
    </>
	);
};
```

### 04. Props
React properties are similar to arguments and parameters in JS.
We can pass props to components, and use them in those components, similarly how we would do with param/args in JS functions    

Passing props to components:   
when rendering a component, pass props with HTML attr. like syntax.   
Example code for passing props to components:   
```javascript
export const App = () => {
	const greeting = "Welcome to our cafe!";
	const coffee = "Coffee";

	return (
		<div className="App">
			<h1>{greeting}</h1>
			<DrinkButtons drinkOne={"Tea"} drinkTwo={coffee} />
		</div>
	);
};
```

Using props inside components:   
props are esentially JS objects, we can access them by creating the parameter __props__  and referring/accessing them as object.Key.   
Example code for using prop inside components:
```javascript
export const DrinkButtons = (props) => {
	return (
		<>
			<h2>Would you like tea or coffee?</h2>
			<div className="button-group">
				<button className="button">{props.drinkOne}</button>
				<button className="button">{props.drinkTwo}</button>
			</div>
		</>
	);
};
```

### 05. Conditionals
Inside JSX we cannot use statements, we can only use expressions.    
This results in limited syntax for conditial logic.    
Conditional logic is very important for dinamic applications    
(i.e. do not render serach result without a search term, empty components will crash the app)

Solutions:  
1. use conditional statement to render a component when there is data available
2. use conditional statement inside the search result component to only try to use data when available

#### Inside JSX
Syntax: we embedd JS expressions in a `{}` block.   

##### Using the __`&&` operator__ instead of __`if` statement__      
 The left side of `&&` must be truthy for the right side expression to render.   
(true && expression will evaluate to expression in JS __&rArr;__ falsy lhs will not render rhs)      
```javascript
export const App = () => {
	const greeting = "Welcome to our cafe!";
	const userDrink = undefined; //undefined as value is used only for representation 

	return (
		<div className="App">
			<h1>{greeting}</h1>
			<DrinkSearch availableDrinks={availableDrinks} />
			{userDrink && (<DrinkChoice drink={userDrink} />)} // if lhs is truthy the component inside `()` will render
		</div>
	);
};
```

##### In JSX we can use the ternary operator to replace the if else statement.    
```javascript
export const App = () => {
	const greeting = "Welcome to our cafe!";
	const userDrink = undefined; // undefined as value is used only for representation 

	return (
		<div className="App">
			<h1>{greeting}</h1>
			<DrinkSearch availableDrinks={availableDrinks} />
			{userDrink ? (<DrinkChoice drink={userDrink} />) : "Please select a drink"}
		</div>
	);
};
```
##### We can also use the ternary operator to dynamically switch between CSS classnames.		
```javascript
export const App = () => {
	const greeting = "Welcome to our cafe!";
	const userDrink = undefined; // undefined as value is used only for representation 

	return (
		<div className="App">
			<h1 className={userDrink ? "small-header" : "big-header"}>{greeting}</h1> // makes the header small if user have selected a drink
			<DrinkSearch availableDrinks={availableDrinks} />
			{userDrink ? (<DrinkChoice drink={userDrink} />) : "Please select a drink"}
		</div>
	);
};
```

#### Conditional return of JSX
##### We can use an `if else` statement outside of the JSX code i.e. in a function	
```javascript
export const App = () => {
	const greeting = "Welcome to our cafe!";
	const userDrink = undefined; // undefined as value is used only for representation 

	const userChoice = (drink) => { // this function returns either a component or a string
		if (drink) {
			return <DrinkChoice drink={drink}/>;
		} else {
				return "Please select a drink";
		}
	}

	return (
		<div className="App">
			<h1 >{greeting}</h1>
			<DrinkSearch availableDrinks={availableDrinks} />
			{userChoice(userDrink)} // we can use the function inside the JSX
		</div>
	);
};
```
##### We can create a component out of the above function
```javascript
// UserChoice component
const UserChoice = (drink) => {
	if (drink) {
		return <DrinkChoice drink={drink}/>;
	} else {
			return "Please select a drink";
	}
};

export const App = () => {
	const greeting = "Welcome to our cafe!";
	const userDrink = undefined; // undefined as value is used only for representation 

	return (
		<div className="App">
			<h1 >{greeting}</h1>
			<DrinkSearch availableDrinks={availableDrinks} />
			<UserChoice drink={userDrink} /> // 
		</div>
	);
};
```

### 06. State
It is a collection of data that stores the state of a page, form or application    
/Data is usually saved in the browser's cash __&rArr;__ this improves browsing experience (faster loading)/   

- allows (with JS together) for an interactive and dynamic website
- used to track and change states across multiple components (on single page apps)
- state is linked to a single component, but can be updated by user actions inside other child components
- state within a component helps to keep track of dynamic data (that can be changed by user action, timers, events: updates)
- in a state we can keep track of any type of variable (string, boolean, etc.)
- state comes with a function to change the state - in functional components this is done by __React hooks__
- after every change in state React will re-render the component in question

To be able to work with states, we need to import the React hook: __`useState`__ (from the React library)    
```javascript
import { useState } from 'react';

export const DrinkButtons = () => {
	const [selectedDrink, serSelectedDrink] = useState('Tea'); // selectedDrink is a state var with an init val of 'Tea'
				// setSelectedDrink is a function to change the value of the state: selectedDrink
	return (<p>Your choice: {selectDrink}</p>); // here we use the state variable to be displayed
};
```

#### Stateful and Statless Components
once we us state in a component it becomes a 'stateful' component / otherwise it is stateless    
__A common pattern in React:__
- a stateful component that maintains it's own state
- state is passed down to child components
- different components have diff purpose: some are handling logic, some are keeping track of state, others displaying contennt, etc.
> it is useful to keep theese things separated (i.e.: UI comps __&rArr;__ displaying content __&rArr;__ no state tracking -- it would impede reusability)
   
```javascript
import { useState } from 'react';

// Stateful parent component
export const FruitSelection = () => {
	const [fruit, setFruits] = useState('Apple');

	return (
		<>
			{fruit && <ShoppingCart content = {fruit} />}
		</>
	);
};

// Stateless child component
export const ShoppingCart = ({fruit}) => {
	return (<p>Shopping cart: {fruit}</p>);
};
```

#### Using Multiple States

- it is best practice to store simple values in the state of a component (do not put all the local state data in a single object)
- for multiple values, use the useState hook multiple times for multiple variables
```javascript
import { useState } from 'react';

export const GameScore = () => {
	const [homeTeamScore, setHomeTeamScore] = useState(0);
	const [visitorTeamScore, setVisitorTeamScore] = useState(0);

	return (
		<>
			<p>Home: {homeTeamScore}</p>
			<p>Visitor: {visitorTeamScore}</p>
		</>
	);
};
```

#### Using Conditionals to Handle Empty States
it is common practice to pass state as prop from one component to another   
> :warning: state might not be the object that the component expects __&rArr;__ TypeError. I.e.: you pass an empty state and data is expected. This could also happen when component gets rendered before receiving the data    

A __conditional statement__ can be a solution to this (se code snippets of stateful/stateless components as an exemple to this as well)
Another way to handle potential empty states is using __optional chaining__ . (used with object wich might or might not have a certain key that weare trying to access. __&rArr;__ instead of throwing an error it will return an 'undefined' and the app will not stop working.   
Example for conditional chaining:    
```javascript
export const DrinkChoice = ({ drink }) => {
	return (
		<>
			<p>{drink?.name}</p>
		</>
	);
};
```
 

