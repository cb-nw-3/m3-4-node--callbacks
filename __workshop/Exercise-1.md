# Questions

# Questions

**With a partner**, answer these questions as completely as possible. Feel free to look at past lecture notes, the web, anything.

Take the time to explain it to each other.

The power of this exercise is in the act of _formulating_ and _explaining_ the concepts to someone else (your teammate).

## One

Run the app. Write out the steps, the _pseudo code_, required to create this app. It doesn't have to be totally accurate, or in the right order.

Only move on to the next question when you have enough detail that you would be able to start coding it yourself.

```
first  the homepage is rendered, with the form element (text input) and the div element showing many entries of a TODO list.

The homepage ejs file accepts an array of strings to print as <li> items in that list.

The form is a text input. When a user presses the submit button, the text in the box is sent to the server (even ""), added as a new array item, and then printed with the other elements of that list.


```

## Two - `server.js`

Take a look at the `server.js` file.

We have a new module in there, `body-parser` that is required on line `4`. What is it for? What is its use-case? What other lines are related to this module?

_The NPM site might be a good place to start. Feel free to provide links as relevant._

```
body-parser is a middleware, like morgan. it parses and validates the inputs before it packages it and populates the req.body object with the contents of the form.

basically a failsafe running all kinds of tests on the input that comes out of the form. there is also many options that can be used to customize what you want out of it. here it is used with default behaviours.

```

## Three - `server.js`

Look at lines `23` and `24`. Explain the methods used. How are they different? What are the usecases for each?

```
.get is used to fetch and "serve" data from the server. you use get to render and show web pages

.post is used to write or edit content to the server. you use it to take data from forms and store it in some way.

```

## Four - `server.js`

Line `6`. That's new. What do you think it's for?

```
This line "imports" the functions handleHomePage, handleFormData, and handle404 from the handlers.js file.

Probably used to compartmentalize and keep the code clean.

"requiring" those functions from that files lets server.js call them as if they were written in the same js file, but without the visual clutter, leaving server.js with only express, middleware, and endpoints stuff.

```

## Five - `handlers.js`

Explain line `1`. Where, why and how is `items` being used?

```
This item array is used to store strings that are sent from the form.

When handleFormData is called, it reads req.body, takes the string and pushes it as the next entry in the items array.

it is also sent to the homepage so that it can render it in the homepage.ejs template.

```

## Six - `handlers.js`

Why is there `redirect` on line `11`;

```
redirect is used after the work is done, to send the user to '/', aka the home page. the homepage doing what it does, reads the now updated items array, and renders it all over again, showing the new item that was just added by handleFormData.

```

## Seven - `handlers.js`

The `handle404` function is a more complex than we've seen thus far, what is the extra functionality for?

```
This seems to contain proofing for different kind of functions calling `handle404`.

This is done because different entities can call an endpoint, like the form action or middleware (body-parser?) and they might not all be able to process html files.

if whatever called the function accepts html, it should render and serve `pages/fourOhFour` with the data of whatever was typed (originalUrl)

if it doesn't accept html, it should send an json object with the error key containing the not found string.

if that is also not supported, it should send the string "not found" in plain text


```

## Eight - `ejs`

Take a look at `homepage.ejs` and `todoInput.ejs`. What is happening in there? Explain line-by-line...

`homepage.ejs`:
first it includes the partial header, which includes the head, and the header of the website.
second, it creates a inputcontainer that includes another partial ejs file, the todoInput. This is the part with a text field and submit button.
the third part is the content, aka the todo list. it renders a unordered list of <li> items.

The <% %> tag holds javascript code that creates a new <li> for every item in the items array, which was passed as data in the `handleHomePage` function.

lastly, it renders the footer template.

`todoInput.ejs`:

this partial ejs file contains a form.

this form has `action='/form-data'` which is what endpoint is going to be triggered when the submit button is pressed.

there is label for the text imput, which has a `name='item'`. This is the key by which the data will be accessed through "req.body" later.

there is also a placeholder that disappears in the text box. this placeholder is "Item Description".

```

```
