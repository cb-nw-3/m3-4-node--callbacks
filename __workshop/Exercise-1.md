# Questions

**With a partner**, answer these questions as completely as possible. Feel free to look at past lecture notes, the web, anything.

Take the time to explain it to each other.

The power of this exercise is in the act of _formulating_ and _explaining_ the concepts to someone else (your teammate).

## One

Run the app. Write out the steps, the _pseudo code_, required to create this app. It doesn't have to be totally accurate, or in the right order.

Only move on to the next question when you have enough detail that you would be able to start coding it yourself.

```
// Answer here
    in server.js
        1. let items = [] //create variable items as empty array, this will be filled with our to do list.
        2. load up dependecies, like express, morgan, nodemon etc.
        3. Create an enpoint for the homepage .get('/', (req, res) =>{res.render('pages/homepage.ejs'){items:items}} );
        4.Create homepage.ejs
    in homepage.ejs
        1.create your html, start with a form, it has a post Method and action = '/submitPost' and an input that has a name of item
        2.Create a ul, this will be our list.
        3.This lists needs to go over the array of items and for each (hehe .forEach) element in the list, create an li element that contains each item.
    let's get back to server.js
        1.Create a .post, we need this to match our form created on step on of the homepage.ejs so .post('/submitPOst')
        2.In the same post method, we need to save what the user submited to a new variable, we can call it item. (need to look up body-parser)
        3.Push the item to the items array in step one.
        4.redirect to the main page and pass {items:items}
    EXTRA
        1.Set up a 404 with .get('*')

```

## Two - `server.js`

Take a look at the `server.js` file.

We have a new module in there, `body-parser` that is required on line `4`. What is it for? What is its use-case? What other lines are related to this module?

_The NPM site might be a good place to start. Feel free to provide links as relevant._

```
body-parser is a middleware that parses the date from incoming requests. In other words, when you have an incoming request(post or put) containing body information, the body-parser will take that date and organize it in various ways, depending on which methods is used. In our case, in line 21, we use BodyParser.json(). That means that in this case, it will create a body object containing the parsed information from the original form that was submitted.We can then use req.body, as is the case in the handleFormDate function (line8). Here we save what was submitted to the form as an object and later push it to our items array.

sources: https://stackoverflow.com/questions/30915424/express-what-is-the-difference-between-req-query-and-req-body
http://expressjs.com/en/resources/middleware/body-parser.html#:~:text=A%20new%20body%20object%20containing%20the%20parsed%20data%20is%20populated,(when%20extended%20is%20true%20).

https://softwareengineering.stackexchange.com/questions/331049/why-do-req-params-req-query-and-req-body-exist/331055#:~:text=req.,such%20a%20%2Fsong%2F%3Asongid%20.&text=req.,properties%20of%20the%20body%20tag.

```

## Three - `server.js`

Look at lines `23` and `24`. Explain the methods used. How are they different? What are the usecases for each?

```
the GET method is used to request date from a specified source. Get ins't secure, as the info in query strings appears in the url.
POST is used send or create new data on a server. The data is sent in the body of the request, making it more secure than get.
You would GET in the case where you don't need info to be secured and to make query's appear in the url, if need be, and use POST when the action implies the creation of new data.

```

## Four - `server.js`

Line `6`. That's new. What do you think it's for?

```
THis is used to pluck out our handler fucntions from the .handlers file that was required. That way, we can call those functions in the appropriate requests.

```

## Five - `handlers.js`

Explain line `1`. Where, why and how is `items` being used?

```
Items is set as an empty array. it is used on line 9. Here, an item (an input in the form), is sent into the array. Then, on line 4, the items array is sent to pages/homepage ejs file, in order for it to be parsed into the html, placing the list items in the list, on the homepage.

```

## Six - `handlers.js`

Why is there `redirect` on line `11`;

```
Because we want to keep the user on the same page, so they can see their list update. So we need to send them page to the homepage. That way, it calls .get("/", handleHomePage) , and in the handleHomePage handler, the items info is sent to the page so it can be rendered.

```

## Seven - `handlers.js`

The `handle404` function is a more complex than we've seen thus far, what is the extra functionality for?

```
The if statements check if "Checks if the specified content types are acceptable, based on the request’s Accept HTTP header field." If it accepts html, it'll render an html file. If it accepts JSON it'll send an object with error:'Not Found'. Otherwise, it'll send plain text. source: https://expressjs.com/en/api.html
```

## Eight - `ejs`

Take a look at `homepage.ejs` and `todoInput.ejs`. What is happening in there? Explain line-by-line...

```
Hompage.ejs:
    Line 1: This include references to the header partial, meaning it places the html contents of the header.ejs file into our html.
    line 3 This include references to the todoInput partial, meaning it places the html contents of the file into our html.
    Line 7. This goes over each item of the items for each array.
    Line 8. It creates a li element for each item in the array and displays inside the li the item (which is a string)
    Line 12 includes the footer partial
TodoInput.ejs
    line 1 tells us the form uses the POST method, meaning that it creates new data, and that it's action is /form-data. So that means on submission, it'll call the .post(/form-data) request.

```

## Nine - `styles.scss`

What are lines `2` to `7` for this file? Where are these values being used? Take a look at `_homepage.scss` as well? What do you notice?

```
// Answer here

```

## Ten - `_homepage.scss`

Line `16`. See if by searching the Sass documentation, you can determine what _exactly_ is going on here. That `#{}` notation very specific to this use-case. Why?

```
you can use sass interpolation to embed the result of SassScript. Here, it is used to make a calculation, in this case, substracting 400 to the width variable.

```
