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

render header (partial)
render body with background image
render HTML
render form
  input type textbox action type = post
  button sumbit
end form
unordered list start style type = none
  create an empty array
  array.push each item posted
  create li for each item
unordered list end

```

## Two - `server.js`

Take a look at the `server.js` file.

We have a new module in there, `body-parser` that is required on line `4`. What is it for? What is its use-case? What other lines are related to this module?

_The NPM site might be a good place to start. Feel free to provide links as relevant._

```
// Answer here

this is a package that parses json, raw responses, text responses and url encoded forms. This is useful for parsing responses received through api calls.
```

## Three - `server.js`

Look at lines `26` and `24`. Explain the methods used. How are they different? What are the usecases for each?

GET is to retrieve information when doing an API call, for example, or entering a URL into Google. POST is the method that creates something, for example, post a new customer to a database, post a new invoice to a database, create a new instance when authenticating.

```
// Answer here

```

## Four - `server.js`

Line `6`. That's new. What do you think it's for?

It looks like you're storing functions in /handlers in a constant.

```
// Answer here

```

## Five - `handlers.js`

Explain line `1`. Where, why and how is `items` being used?

```
// Answer here

It's a constant that holds an empty array of items. As items are added to the list, they get pushed into the array.

## Six - `handlers.js`

Why is there `redirect` on line `11`;

```

// Answer here

I believe it refreshes the form, and ensures the user stays on the same page, instead of a page only showing the list.

```

## Seven - `handlers.js`

The `handle404` function is a more complex than we've seen thus far, what is the extra functionality for?

```

// Answer here

It looks like this is to reject data being passed in that is anything but text. could this be a security measure against code injection?

## Eight - `ejs`

Take a look at `homepage.ejs` and `todoInput.ejs`. What is happening in there? Explain line-by-line...

```

<%- include('../partials/header') %> - include the header partial
<div class='input-container'> - Open container to hold input form.
    <%- include('../partials/todoInput') %> - inlclude the todoInput partial
</div> - close container
<div class='content'> - Open content div
    <ul class='todo-list'> - unordered list
        <% items.forEach(item => { %> - for each looping through the items array.
            <li class='todo-list--item'><%= item %></li> - create li for each item
        <% }); %> - end foreach
    </ul> - end ordered list
</div> - close div
<%- include('../partials/footer') %> - include the footer partial.

```

```

```
