# Questions

**With a partner**, answer these questions as completely as possible. Feel free to look at past lecture notes, the web, anything.

Take the time to explain it to each other.

The power of this exercise is in the act of _formulating_ and _explaining_ the concepts to someone else (your teammate).

## One

Run the app. Write out the steps, the _pseudo code_, required to create this app. It doesn't have to be totally accurate, or in the right order.

Only move on to the next question when you have enough detail that you would be able to start coding it yourself.

```
1. list out the dependencies to create a server
2. create the endpoints for the html
use .get to create an endpoint for the homepage and to handle 404
use .post to handle the form data that is received and posted to the page
3. create a .listen to set a port for your live server

```

## Two - `server.js`

Take a look at the `server.js` file.

We have a new module in there, `body-parser` that is required on line `4`. What is it for? What is its use-case? What other lines are related to this module?

_The NPM site might be a good place to start. Feel free to provide links as relevant._

```
found from:
https://www.npmjs.com/package/body-parser
https://expressjs.com/en/resources/middleware/body-parser.html

body-parser converts the parsed input data into a form.
like 21 uses body-parser ' .use(bodyParser.json())'

```

## Three - `server.js`

Look at lines `26` and `24`. Explain the methods used. How are they different? What are the usecases for each?

```
GET is used to request data from a specific resource.
POST is used to send loads of data to a server from a specific resource.

```

## Four - `server.js`

Line `6`. That's new. What do you think it's for?

```
It's saying that if any of those functions in the curly brackets are called then the handlers.js must be used since it contains the information about the functions.

```

## Five - `handlers.js`

Explain line `1`. Where, why and how is `items` being used?

```
When the function handleFormData gets triggered, it will push the item into the items array which results in an item appearing in the todo list.

```

## Six - `handlers.js`

Why is there `redirect` on line `11`;

```
There is a redirect to the homepage so that the user is not stuck on /form-data. Once they're redirected to the homepage it should be updated with the latest data.

```

## Seven - `handlers.js`

The `handle404` function is a more complex than we've seen thus far, what is the extra functionality for?

```
It seems like the handle404 function was created to be used for different sceenarios. It will return specific errors depending on the file type.

```

## Eight - `ejs`

Take a look at `homepage.ejs` and `todoInput.ejs`. What is happening in there? Explain line-by-line...

```
 `homepage.ejs`
 - renders the headers ejs file from partials folder
 - renders the todoInput ejs file from partials folder
 - there is a foreach loop that will add an item (as an li element) to the todo list
  - renders the footer ejs file from partials folder


`todoInput.ejs`
- a form with the POST method that calls for '/form-data' which will trigger the handleFormData function.
- form objects (input, button) to have the form be functional
```
