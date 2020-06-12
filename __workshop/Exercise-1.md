# Questions

**With a partner**, answer these questions as completely as possible. Feel free to look at past lecture notes, the web, anything.

Take the time to explain it to each other.

The power of this exercise is in the act of _formulating_ and _explaining_ the concepts to someone else (your teammate).

## One

Run the app. Write out the steps, the _pseudo code_, required to create this app. It doesn't have to be totally accurate, or in the right order.

Only move on to the next question when you have enough detail that you would be able to start coding it yourself.

```
// Answer here

We need the dependencies in the server.js and also the functions related to the endpoints.

.get('/', handleHomepage) // This is the setup for the home page.
.post()                   // This post data to the "TODO list".
get('*', handle404)       // This redirects anything not defined.

```

## Two - `server.js`

Take a look at the `server.js` file.

We have a new module in there, `body-parser` that is required on line `4`. What is it for? What is its use-case? What other lines are related to this module?

_The NPM site might be a good place to start. Feel free to provide links as relevant._

```
Basically what the body-parser is which allows express to read the body and then parse that into a Json object that we can understand. // Taken from Stack-Overflow

It is used on line 21

Source: https://www.npmjs.com/package/body-parser#options-2

```

## Three - `server.js`

Look at lines `26` and `24`. Explain the methods used. How are they different? What are the usecases for each?

```
(line 26) // This renders "homepage.ejs".
(line 27) // This adds new data from our array and displays it.

```

## Four - `server.js`

Line `6`. That's new. What do you think it's for?

```
// This line imports js code from the handers.js file, this makes our "server.js" file cleaner, by having our functions on another JS file.

```

## Five - `handlers.js`

Explain line `1`. Where, why and how is `items` being used?

```
// It is an empty array from which we add new item from question "three".

```

## Six - `handlers.js`

Why is there `redirect` on line `11`;

```
// Because it needs to be redirected to the homepage for display.

```

## Seven - `handlers.js`

The `handle404` function is a more complex than we've seen thus far, what is the extra functionality for?

```
// This is different from the previous workshop. This accept HTML and JSON file, and returns the appropriate error message.

```

## Eight - `ejs`

Take a look at `homepage.ejs` and `todoInput.ejs`. What is happening in there? Explain line-by-line...

```
homepage.ejs // A list of items that were entered by the viewer is pushed into the array from "question 5" array which is rendered in the homepage.
​
todoInput.js // This file contains the "<form>" tags with the POST method which is required in "server.js".

```
