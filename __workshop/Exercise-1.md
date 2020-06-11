# Questions

**With a partner**, answer these questions as completely as possible. Feel free to look at past lecture notes, the web, anything.

Take the time to explain it to each other.

The power of this exercise is in the act of _formulating_ and _explaining_ the concepts to someone else (your teammate).

## One

Run the app. Write out the steps, the _pseudo code_, required to create this app. It doesn't have to be totally accurate, or in the right order.

Only move on to the next question when you have enough detail that you would be able to start coding it yourself.

```
// Answer here
1. Install and configure express
It could be using. npx express-generator

2. Configure views = ejs, server name: server.js, port = 8000 address, static files, midleware

server file should have this:

const express = require('express');
const bodyParser = require('body-parser');
const morgan = require('morgan');


3. configure yarn.lock file  yarn init

4. write the code related to the app
  a) create the VIEWS / templates ejs pages and partials
  b) configure the endpoints
  c) write the css scss
  d) javascrit functions

5. FRONT-END
Form with an input field and a submit button, submit use a post method to send the info to the server, creating a new item on the list

```

## Two - `server.js`

Take a look at the `server.js` file.

We have a new module in there, `body-parser` that is required on line `4`. What is it for? What is its use-case? What other lines are related to this module?

_The NPM site might be a good place to start. Feel free to provide links as relevant._

```
// Answer here

Tell body parser to extracts date from the form on the body element and add it to the body object on the request

Taken from https://www.npmjs.com/package/body-parser



Taken from https://stackoverflow.com/questions/38306569/what-does-body-parser-do-with-express#:~:text=js%20version%204%20and%20above,body%20.&text=This%20body%2Dparser%20module%20parses,submitted%20using%20HTTP%20POST%20request.

To handle HTTP POST request in Express.js you need to install middleware module called body-parser.
body-parser extract the entire body portion of an incoming request stream and exposes it on req.body.
```

## Three - `server.js`

Look at lines `23` and `24`. Explain the methods used. How are they different? What are the usecases for each?

```
// Answer here
endpoints

app.get() method specifies a callback function that will be invoked whenever there is an HTTP GET request with a path ('/') relative to the site root
taken from : https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/Introduction

GET carries request parameter appended in URL string while POST carries request parameter in message body which makes it more secure way of transferring data from client to server in http protocol.

GET is used to request data from a specified resource.
POST is used to send data to a server to create/update a resource.

```

## Four - `server.js`

Line `6`. That's new. What do you think it's for?

const { handleHomePage, handleFormData, handle404 } = require('./handlers');

```
// Answer here
we are using anothe file to define our functions = handlers file handlers.js
export from hanlers.js
importing to server using require('./handlers') and assigning it to { handleHomePage, handleFormData, handle404 }
```

## Five - `handlers.js`

Explain line `1`. Where, why and how is `items` being used?

```
// Answer here
"use strict";
It makes mandatory to declare the variables

```

## Six - `handlers.js`

Why is there `redirect` on line `11`;

```
// Answer here
When posting the data in the server, it tells the server to tell the browser to return to home and show the changes

```

## Seven - `handlers.js`

The `handle404` function is a more complex than we've seen thus far, what is the extra functionality for?

```
// Answer here

```

## Eight - `ejs`

Take a look at `homepage.ejs` and `todoInput.ejs`. What is happening in there? Explain line-by-line...

```
// Answer here

```

## Nine - `styles.scss`

What are lines `2` to `7` for this file? Where are these values being used? Take a look at `_homepage.scss` as well? What do you notice?

```
// Answer here

```

## Ten - `_homepage.scss`

Line `16`. See if by searching the Sass documentation, you can determine what _exactly_ is going on here. That `#{}` notation very specific to this use-case. Why?

```
// Answer here

```
