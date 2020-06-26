# Questions

**With a partner**, answer these questions as completely as possible. Feel free to look at past lecture notes, the web, anything.

Take the time to explain it to each other.

The power of this exercise is in the act of _formulating_ and _explaining_ the concepts to someone else (your teammate).

## One

Run the app. Write out the steps, the _pseudo code_, required to create this app. It doesn't have to be totally accurate, or in the right order.

Only move on to the next question when you have enough detail that you would be able to start coding it yourself.

```
// Answer here
-Create basic node server.
-Write homepage html and style it.
-Do the same for a 404 page.
-For the last two, use ejs templates if useful
-Make a get / in a server.js file and make it render the html.
-The page should have a form
-The information from the form should be pushed into an array via a post request.
-The page should be rendered once again with the updated array on it with a redirect.
-And so on...
```

## Two - `server.js`

Take a look at the `server.js` file.

We have a new module in there, `body-parser` that is required on line `4`. What is it for? What is its use-case? What other lines are related to this module?

_The NPM site might be a good place to start. Feel free to provide links as relevant._

```
// Answer here
The module `body-parser` is a middleware. That means it's functions have access to both the user's request and response and can modify them. This particular one `parses` the request body (req.body) before the handlers proceed with the request. From what I understand, parsing is making data available and breaking it down in parts. In this case, we do this to make it easier to work with. For example, if the req.body is some sort of form filled out by a user, `body-parser` would break it into the different information in a key-value pair format. This makes it easy to get only the value needed to proceed with a specific response. 

Other lines related are: Lines 21 in server.js, line 8 in handlers.js and line 15 in package.json

```

## Three - `server.js`

Look at lines `26` and `27`. Explain the methods used. How are they different? What are the usecases for each?

```
// Answer here
These two lines are both http requests. Line 26 determines what happens when the user enter the root directory url which is represented by '/'. In this case, it 'gets' the handleHomePage handler from the server. Line 27 is a bit different. .post is a method that 'posts' data to the server. In this case, the form data.

```

## Four - `server.js`

Line `6`. That's new. What do you think it's for?

```
// Answer here
It's a neat way of putting all the handler methods on one seperate file. Here we 'import' to the server, the three handlers stated in the handlers.js file. See the module.export at the end of the file.
```

## Five - `handlers.js`

Explain line `1`. Where, why and how is `items` being used?

```
// Answer here
items is simply an empty array. Whenever handleformData is called, an item object is pushed into the array and the root directory is called which in turn the handleHomePage takes over. This last one is passed the item array which hold the newly pushed object. That renders the homepage with a new object as a list item.

```

## Six - `handlers.js`

Why is there `redirect` on line `11`;

```
// Answer here
As mentioned in the last question, redirecting to the root directory will ultimately render the homepage once more but with an updated item array and therefor, an updated list.

```

## Seven - `handlers.js`

The `handle404` function is a more complex than we've seen thus far, what is the extra functionality for?

```
// Answer here
The two if statements checks information in the http header are if the 'html' type or 'json' type. Based on the answers, it will either render pages/fourOhFour  or send an error.

```

## Eight - `ejs`

Take a look at `homepage.ejs` and `todoInput.ejs`. What is happening in there? Explain line-by-line...

```
// Answer here
The homepage is a standard ejs file. It's a template for the homepage. The elements in the to-do list is past as list items by a forEach function.

```
