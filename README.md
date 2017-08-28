# Middleware

## What are express middlewares?
middlewares are functions that have access to the **request object (req)**, **the response object (res)**, and the next middleware function in the application’s request-response cycle. The next middleware function is commonly denoted by a variable named next.
## What functionality do they provide?
Middleware functions can perform the following tasks:
* Execute any code.
* Make changes to the request and the response objects.
* End the request-response cycle.
* Call the next middleware function in the stack.


If the current middleware function does not end the request-response cycle, it must call **next()** to pass control to the next middleware function. Otherwise, the request will be left hanging.

## What are some examples of useful express middleware and how do you use them?

### [Morgan](https://www.npmjs.com/package/morgan)
we are going to setup our application to report and generate logs files about the user’s requests. To do this let’s use the module morgan which is a middleware for generating request’s logs in the server.
* To install it type the following command<br>
```npm install morgan--save  ```

``` js
const express = require('express');
const morgan = require('morgan');
const fs = require('fs');
const path = require('path');

const app = express();

const accessLogStream = fs.createWriteStream(
  path.join(__dirname, '..', 'logs-demo', 'access.log'),
  { flags: 'a' }
);

app.use(morgan('combined', { stream: accessLogStream }));

```



### [Body Parser](https://www.npmjs.com/package/body-parser)
Parse incoming request bodies in a middleware before your handlers, available under the req.body property.

* To install it type the following command<br>
```npm install body-parser--save  ```


``` js
const express = require('express');
const bodyParser = require('body-parser');

const app = express();

app.use(bodyParser.json());

```

### [Helmet](https://www.npmjs.com/package/helmet)
let’s include a very important module, which is a security middleware that handles several kinds of attacks in the HTTP/HTTPS protocols. This module is called helmet which is a set of nine internal middlewares, responsible to treat the following HTTP settings:

* Configures the Content Security Policy;
* Removes the header X-Powered-By that informs the name and the version of a server;
* Configures rules for HTTP Public Key Pinning;
* Configures rules for HTTP Strict Transport Security;
* Treats the header X-Download-Options for Internet Explorer 8+;
* Disables the client-side caching;
* Prevents sniffing attacks on the client Mime Type;
* Prevents ClickJacking attacks;
* Protects against XSS (Cross-Site Scripting) attacks.


To install it, run the command<br>
```npm install helmet--save```  

``` js
const express = require("express");
const helmet = require("helmet");

const app = express();

app.use(helmet());
```
