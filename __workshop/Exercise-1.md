# Questions

**With a partner**, answer these questions as completely as possible. Feel free to look at past lecture notes, the web, anything. 

Take the time to explain it to each other. 

The power of this exercise is in the act of _formulating_ and _explaining_ the concepts to someone else (your teammate).

## One

Run the app. Write out the steps, the _pseudo code_, required to create this app. It doesn't have to be totally accurate, or in the right order.

Only move on to the next question when you have enough detail that you would be able to start coding it yourself.

```
// Answer here


The is a header with todo list
This is a form input with a submit button

and then there div with a bunch of items in it, presumably listed as a bunch of li elements but who knows

when the submit button is hit, POST is probably called and the form data in "item description" is added to an array, the page is refreshed with the new array?

the page displays the items in the array/ 
```

## Two - `server.js`

Take a look at the `server.js` file.

We have a new module in there, `body-parser` that is required on line `4`. What is it for? What is its use-case? What other lines are related to this module?

_The NPM site might be a good place to start. Feel free to provide links as relevant._



```
// Answer here
from the NPm site 
https://www.npmjs.com/package/body-parser
Parse incoming request bodies in a middleware before your handlers, available under the req.body property.


The use case here is to parse out the text that we get from the submit and form, it parses it into JSON and then stores that JSON object into the items array.

Related lines: 
  .post('/form-data', handleFormData)
const { handleHomePage, handleFormData, handle404 } = require('./handlers');

 and then assorted functions in .handlers
```

## Three - `server.js`

Look at lines `23` and `24`. Explain the methods used. How are they different? What are the usecases for each?



```
// Answer here

  .get('/', handleHomePage)
  .post('/form-data', handleFormData)

  these are simple endpoints that handle the GET and POST requests, the get return the homepage and the .post intakes the input form data and pushes the JSON data into the array of items (and then reloads the page).


```

## Four - `server.js`

Line `6`. That's new. What do you think it's for?

```
// Answer here
const { handleHomePage, handleFormData, handle404 } = require('./handlers');
This is to include the handlers.js file which contains the hanlder variables,

It is a Destructuring assignment used to import fucntions from the handler.js module.  Notably, all three are enumerated in module.exports and we suspect that you could not, for example, call items because it is not declared in module.exports. 


(https://stackoverflow.com/questions/35415978/syntax-const-variablename-can-anyone-explain-or-point-me-into-the-right-d)



```
## Five - `handlers.js`

Explain line `1`. Where, why and how is `items` being used?

```

// Answer here
Items is our list.  It is an array where we store the JSON that we get from the form input.  It is returned in handleHomePage 



```

## Six - `handlers.js`

Why is there `redirect` on line `11`;

```
// Answer here
Because when you enter a new item into the array, you need to re-load the page to see the new item list.  

We don't have dyaminc reloading of elements so we have to reload the whole page.

``` 

## Seven - `handlers.js`

The `handle404` function is a more complex than we've seen thus far, what is the extra functionality for?

```
1) .use is invoked when the .get and .post lines are passed over

handle404 is invoked, but we can't actually get it to work with blank json, or blank text.  
// Answer here

```

## Eight - `ejs`

Take a look at `homepage.ejs` and `todoInput.ejs`. What is happening in there? Explain line-by-line...

```
// Answer here

headers are included at the top, which is an ejs template file, whicn includes the head informatiton and thre title,.

we have our input container div with has our input partial, which calls the POST method, passing the form data as item.

Then in the content div, we loop through the items array, which has been passed in the handlers.js code as homepage call, and render out each JSON item as a <li>.

And then finally, the footer partials which have almost nothing - a footer tag and the end body tag.  

```

## Nine - `styles.scss`

What are lines `2` to `7` for this file? Where are these values being used? Take a look at `_homepage.scss` as well? What do you notice?

```
// Answer here

```

## Ten - `_homepage.scss`

Line `16`. See if by searching the Sass documentation, you can determine what _exactly_ is going on here. That `#{}` notation very specific to this use-case. Why?

```
This is used to shrink the size of the text input box by 60 px, to accomodate the submit.

Question - the input box in CSS lives outside of the content tag - how does it know the content width?
// Answer here

```







