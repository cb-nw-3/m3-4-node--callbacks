# Questions
​
**With a partner**, answer these questions as completely as possible. Feel free to look at past lecture notes, the web, anything.
​
Take the time to explain it to each other.
​
The power of this exercise is in the act of _formulating_ and _explaining_ the concepts to someone else (your teammate).
​
## One
​
Run the app. Write out the steps, the _pseudo code_, required to create this app. It doesn't have to be totally accurate, or in the right order.
​
Only move on to the next question when you have enough detail that you would be able to start coding it yourself.
​
```
// Answer here
require dependencies /morgan /express to create a server
create endpoints that lead to html/partials
​
  created a partial for footer, form and header and the to-do-list
  header partial is linked to the css styles
​
  .get('/', handleHomepage) // create an endpoint with handler
  .post() // handle form data and post onto page
  .get('*', handle404) // create an endpoint for 404
​
  .listen(PORT...) // set the port for your live server
​
```
​
## Two - `server.js`
​
Take a look at the `server.js` file.
​
We have a new module in there, `body-parser` that is required on line `4`. What is it for? What is its use-case? What other lines are related to this module?
​
_The NPM site might be a good place to start. Feel free to provide links as relevant._
​
```
// Answer here
found some info here: https://www.npmjs.com/package/body-parser#options-2
and https://expressjs.com/en/resources/middleware/body-parser.html
​
body-parser is middleware to validate user input used in combination with the express package. (seen on line 18)
​
the use case for the app will parse for input that are in json format, with no additional options
​
​
```
​
## Three - `server.js`
​
Look at lines `23` and `24`. Explain the methods used. How are they different? What are the usecases for each?
​
```
// Answer here
​
(line 23) calls to the .get() method with the handler to render the homepage.ejs file
(line 24) calls to the .post() method with a handler called handleFormData which will add new data into the items array
​
.get() retrieves data that we already have, and .post() adds new data that we pass on the list
​
```
​
## Four - `server.js`
​
Line `6`. That's new. What do you think it's for?
​
```
// Answer here
​
this line imports js code from the handers.js file, instead of having to write the handler functions within
the `server.js` file
​
in the `handlers.js` file has the modules.exports to export the functions
​
​
```
​
## Five - `handlers.js`
​
Explain line `1`. Where, why and how is `items` being used?
​
```
// Answer here
​
this is as empty array from which we can push new data into from our .post() method that calls on the
handleFormData callback function
​
```
​
## Six - `handlers.js`
​
Why is there `redirect` on line `11`;
​
```
// Answer here
because when new data is entered it will not be rendered on the handleFormData function, it needs
to be redirected to the `/` or homepage where the handleHomePage function will render the list with the
updated [items] array
​
```
​
## Seven - `handlers.js`
​
The `handle404` function is a more complex than we've seen thus far, what is the extra functionality for?
​
```
// Answer here
​
from what we could see, there are extra steps that will send a response based on what the app will accept
which are html files or json (for POST)
​
also to note, any route that we specify that does not exist will by default render the 404 page
because we think the accepts html/json either way
​
​
```
​
## Eight - `ejs`
​
Take a look at `homepage.ejs` and `todoInput.ejs`. What is happening in there? Explain line-by-line...
​
```
// Answer here
For homepage.ejs, we call on a few partials to fill in the header and the form followed by some
content, which is in this case the list of items that were submitted in the form. Gets passed into the `items` array which is rendered in handleHomepage
​
For todoInput.ejs, this file contains the `<form>` tags with the POST method linked to the
/form-data ACTION which is required in the .post() method in the server.js as our expression argument.
​
​
```
​
## Nine - `styles.scss`
​
What are lines `2` to `7` for this file? Where are these values being used? Take a look at `_homepage.scss` as well? What do you notice?
​
```
// Answer here
​
this is the equivalent of declaring variables in .css files like
​
body {
  color: var(--primary-color);
}
​
these variables are used accross multiple selector classes in the .scss files
like _homepage.scss
​
​
```
​
## Ten - `_homepage.scss`
​
Line `16`. See if by searching the Sass documentation, you can determine what _exactly_ is going on here. That `#{}` notation very specific to this use-case. Why?
​
```
// Answer here
​
the `#{}` notation is just like the javascript interpolation in the recent ES6 where we
use `${}` so we call variables into expressions.
​
For example line 16
​
width: calc(#{$content-width} - 60px);
​
the variable content-width has the value of 400px, but it needs to be in an expression
for it to be calculated in the calc function

```







