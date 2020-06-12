# Questions

**With a partner**, answer these questions as completely as possible. Feel free to look at past lecture notes, the web, anything.

Take the time to explain it to each other.

The power of this exercise is in the act of _formulating_ and _explaining_ the concepts to someone else (your teammate).

## One

Run the app. Write out the steps, the _pseudo code_, required to create this app. It doesn't have to be totally accurate, or in the right order.

Only move on to the next question when you have enough detail that you would be able to start coding it yourself.

```
// Answer here
write out HTML partials in ejs, create page that utilizes them
write one more partial -> TODO form
.get /
  render the html w/ ** the form-data **
.use * to handle all non-existent URLs to default 404 page
  app should output list of items (to do list)

```

## Two - `server.js`

Take a look at the `server.js` file.

We have a new module in there, `body-parser` that is required on line `4`. What is it for? What is its use-case? What other lines are related to this module?

_The NPM site might be a good place to start. Feel free to provide links as relevant._

```
// Answer here
In handlers.js - handlerFormData creates a { variable } (the todo item) that uses req.body, which is used for body-parser which is ultimately used to save the details.
(If I am not mistaken, this is why the todo item that the user puts in is saved on the page even after clearing cache)

```

## Three - `server.js`

Look at lines `26` and `24`. Explain the methods used. How are they different? What are the usecases for each?

```
// Answer here
GET method is used to request data from a specific resource whereas
POST is used to send data to a server
https://www.w3schools.com/tags/ref_httpmethods.asp

```

## Four - `server.js`

Line `6`. That's new. What do you think it's for?

```
// Answer here

It requires the endpoints to use the functions provided in handlers.js so instead of writing the arrow functions in the .get(), they are imported from the handlers.js file

```

## Five - `handlers.js`

Explain line `1`. Where, why and how is `items` being used?

```
// Answer here

Items (todo items added by the user) are pushed to the array, that is generated onto the TODO list through handleFormData and the .post() method in servers.js.

```

## Six - `handlers.js`

Why is there `redirect` on line `11`;

```
// Answer here
After submiting an item into the todo list, the redirect will reload the homepage, which will have the updated todo list, and the input will be empty and ready for the next item.

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
The first part is using the <%- include %> for the header partial which generates the <!DOCTYPE> <html> <head> <body> tags to start the page

The todoInput partial that is <%- include %> creates the form on the home page

Back in the homepage.ejs a <ul> is created using a forEach() ran on the items to create a <li> per item in the list

And the final part is the <%- include %> of the footer partial to close off the document

```
