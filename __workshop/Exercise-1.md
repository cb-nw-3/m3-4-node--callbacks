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
Create an HTML file that includes a header, as well as a form with a submit button. We create a div that includes an unordered list.

The form should use the POST method. It will create an express POST method in the server where the request will be handled.

Inside the server file, each item that is written by the user gets passed into an array. Each time an item is added, a <li> item is created and rendered to the homepage by reloading the page.


```

## Two - `server.js`

Take a look at the `server.js` file.

We have a new module in there, `body-parser` that is required on line `4`. What is it for? What is its use-case? What other lines are related to this module?

_The NPM site might be a good place to start. Feel free to provide links as relevant._

```
// Answer here

body-parser is an npm package and a parsing middleware. It sits between the request to the server and the handler functions that are supposed to execute when they receive the data.

It is used to refine the data that is being passed to the 'req.body' object in order to be able to extract the data that you need.

```

## Three - `server.js`

Look at lines `26` and `24`. Explain the methods used. How are they different? What are the usecases for each?

```
// Answer here
GET

The GET method is used to retrieve data from the server. With GET you can pass additional data but only through the URL.

POST

The POST method is used to add data to the server. When you make a POST request, you can send along additional data when you use it.

```

## Four - `server.js`

Line `6`. That's new. What do you think it's for?

```
// Answer here

At line 6, we are requiring the object that is being exported from handler.js and deconstructing it so as to extracting each function from the object.

```

## Five - `handlers.js`

Explain line `1`. Where, why and how is `items` being used?

```
// Answer here

'item' is an array that stores each value that the user submits through the HTML form.

```

## Six - `handlers.js`

Why is there `redirect` on line `11`;

```
// Answer here

To rendered the HTML newly added items.

```

## Seven - `handlers.js`

The `handle404` function is a more complex than we've seen thus far, what is the extra functionality for?

```
// Answer here

The function checks if the request accepts a certain type of data and depending on that data, it will return a response that matches it.

```

## Eight - `ejs`

Take a look at `homepage.ejs` and `todoInput.ejs`. What is happening in there? Explain line-by-line...

```
// Answer here

1. Includes the header partial that includes the html code for the header

2-4. Includes the form and submit button from the appropriate partial.

5-11. Loops through the array of items provided by the user and creates <li> items for each item.

12. Includes the footer partial.

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
