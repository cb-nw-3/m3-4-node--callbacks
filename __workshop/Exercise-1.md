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

3. configure yarn.lock file  yarn init

4. write the code related to the app
  a) create the VIEWS / templates ejs pages and partials
  b) configure the endpoints
  c) write the css scss
  d) javascrit functions

5. FRONT-END
Form with an input field and a submit button, submit use a post method to send the info to the server, creating a new item on the list

server file should have this:

const express = require('express');
const bodyParser = require('body-parser');
const morgan = require('morgan');

//This was added on exercise review with Josh Comeau
What happens when running the application:

1. render de homepage.ejs
2. Each time a new Item is added to the To Do List it send a POST status 302 the browser recieves the 302
3. redict to home page / refreshing the new item

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
When posting the data in the server, it tells the server to return to home and show the changes

```

## Seven - `handlers.js`

The `handle404` function is a more complex than we've seen thus far, what is the extra functionality for?

```
// Answer here

req.accepts(types)
Checks if the specified content types are acceptable

In this case it checks if we are reciving HTML and then renders the 404 page

```

## Eight - `ejs`

Take a look at `homepage.ejs` and `todoInput.ejs`. What is happening in there? Explain line-by-line...

```
// Answer here

This is the homepage.ejs
<%- include('../partials/header') %> ==>  imports the header from partials/header.ejs
<div class='input-container'>  ==> creates a div with the class input-container
    <%- include('../partials/todoInput') %> ==> imports the todoInput from partials/todoInputs.ejs
</div> ==> closes the div
<div class='content'> ==> open a new div class = content
    <ul class='todo-list'> ==> creates a ul with the class todo-list
        <% items.forEach(item => { %> => run a loop, for each element of items
            <li class='todo-list--item'><%= item %></li>  ==> create a li with the class todo-list--items with the item given by the loop
        <% }); %>  ==> close the loop
    </ul>  ==> close the ul
</div> close the div
<%- include('../partials/footer') %> ==>  imports the footer from partials/footer.ejs

this is the todoInputs,ejs
<form method='POST' action='/form-data'>  ==> defines a form with post method and tell the browser to go to /form-data endpoint
    <label for='item'>TODO Item</label> ==>  creates the label
    <input type='text' name='item' placeholder='Item Description' /> => creates and input type text and name item
    <button type='submit'>Submit</button>  ==> creates a button type submit
</form> =>  close the form
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
