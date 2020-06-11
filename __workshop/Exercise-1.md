# Questions

**With a partner**, answer these questions as completely as possible. Feel free to look at past lecture notes, the web, anything.

Take the time to explain it to each other.

The power of this exercise is in the act of _formulating_ and _explaining_ the concepts to someone else (your teammate).

## One

Run the app. Write out the steps, the _pseudo code_, required to create this app. It doesn't have to be totally accurate, or in the right order.

Only move on to the next question when you have enough detail that you would be able to start coding it yourself.

```
// Answer here
get /
  render the html
  should have a form
  should have list of items

post /
  item entered on the form should be added to the list on the backend to persist data
  item should be displayed back to the page

```

## Two - `server.js`

Take a look at the `server.js` file.

We have a new module in there, `body-parser` that is required on line `4`. What is it for? What is its use-case? What other lines are related to this module?

_The NPM site might be a good place to start. Feel free to provide links as relevant._

```
// Answer here
https://www.npmjs.com/package/body-parser

It is a middleware that validates incoming post request's body. The body can contain unwanted values or properties from the client side
and body-parser validates its contents.
line 21 is when this module is applied to the express pipeline
```

## Three - `server.js`

Look at lines `26` and `24`. Explain the methods used. How are they different? What are the usecases for each?

```
// Answer here
get method is used to fetch something from the server and post is used to create something on the server.
get will expose all parameters in the url while post will have a body for a more secure way of data transfer from client to server.

```

## Four - `server.js`

Line `6`. That's new. What do you think it's for?

```
// Answer here
it looks like an object deconstruction where we assign the properties of the object on the right side to the specified properties on the left side.
```

## Five - `handlers.js`

Explain line `1`. Where, why and how is `items` being used?

```
// Answer here
items acts as the database to persist the items being added on the list.

```

## Six - `handlers.js`

Why is there `redirect` on line `11`;

```
// Answer here
redirect is needed to redirect the user back to the homepage after the post request, if it is omitted, the request will look like it never finished and the server never responded to the client.
```

## Seven - `handlers.js`

The `handle404` function is a more complex than we've seen thus far, what is the extra functionality for?

```
// Answer here
it checks for the acceptable Content-type based on the request's accept http header and returns the best match.
```

## Eight - `ejs`

Take a look at `homepage.ejs` and `todoInput.ejs`. What is happening in there? Explain line-by-line...

```
// Answer here
homepage.ejs includes the header partial at the very top.
todoInput.ejs is also included and placed in its own container div.
todoInput.ejs is just a form to send out post request to add new items on the to do lit
homepage.ejs then display the to do list by iterating through the items array sent by the server
footer is included at the bottom
```
