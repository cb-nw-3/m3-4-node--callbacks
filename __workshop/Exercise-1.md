# Questions

**With a partner**, answer these questions as completely as possible. Feel free to look at past lecture notes, the web, anything.

Take the time to explain it to each other.

The power of this exercise is in the act of _formulating_ and _explaining_ the concepts to someone else (your teammate).

## One

Run the app. Write out the steps, the _pseudo code_, required to create this app. It doesn't have to be totally accurate, or in the right order.

Only move on to the next question when you have enough detail that you would be able to start coding it yourself.

```
get the homepage, render homepage with partials , have an object to store data that is being inputted and when the item is submitted to the object, then item is POSTED to the homepage in order to view current items list and the input on the input tag is DELETED and the form is ready to accept any new items.

```

## Two - `server.js`

Take a look at the `server.js` file.

We have a new module in there, `body-parser` that is required on line `4`. What is it for? What is its use-case? What other lines are related to this module?

_The NPM site might be a good place to start. Feel free to provide links as relevant._

```
1- to parse bodies into the middleware before the handlers have been fired; these are accessible through the use of req.body (https://www.npmjs.com/package/body-parser#bodyparserjsonoptions)

2- The other lines that are related to this module are found in line 21-22; Both bodyParser.json and urlencoded Returns middleware that only parses json and only looks at requests where the Content-Type header matches the type option (from NPM).

```

## Three - `server.js`

Look at lines `26` and `27`. Explain the methods used. How are they different? What are the usecases for each?

```
Line 26: method used is handleHomePage,Line 27: method used is handleFormData;
handleHomePage renders the homepage.ejs with an object that contains an array of items;
handleFormData parses information from the body and pushes new items to the object containing an array of items and then it updates the homepage with the new added items;
handleHomePage gets data and handleFormData creates a list of data.

```

## Four - `server.js`

Line `6`. That's new. What do you think it's for?

```
Line 6 is an object that contains all your handlers and it is made accessible to the server when it is getting the homepage and posting new body data or using your 404 page when there is an error.

```

## Five - `handlers.js`

Explain line `1`. Where, why and how is `items` being used?

```
Line 1 is an empty array of items, it is used in handleHomePage and handleFormData; In handleHomePage it is used to render a new list of items by accessing the object that contains the array of items; In handleFormData it is used to create new items by pushing these new items into the array of items.

```

## Six - `handlers.js`

Why is there `redirect` on line `11`;

```
Redirect is found here in the event that item is recognized by the bodyParser and it allocates a value of true, then it would redirect to a specified pathway, in this case, the homepage; but if it was negative, then the handle404 would be triggered and send an error message.

```

## Seven - `handlers.js`

The `handle404` function is a more complex than we've seen thus far, what is the extra functionality for?

```


```

## Eight - `ejs`

Take a look at `homepage.ejs` and `todoInput.ejs`. What is happening in there? Explain line-by-line...

```
// Answer here

```

## Nine - `styles.scss`

What are lines `2` to `7` for this file? Where are these values being used? Take a look at `_homepage.scss` as well? What do you notice?

```
// NOT TO BE ANSWERED AS PER JOSH //

```

## Ten - `_homepage.scss`

Line `16`. See if by searching the Sass documentation, you can determine what _exactly_ is going on here. That `#{}` notation very specific to this use-case. Why?

```
// Answer here

```
