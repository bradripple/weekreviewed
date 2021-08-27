# weekreviewed


## controllers and routes

functions that execute when a client sends a request. Routes set the url address

```
// Controller
const home = (req, res) => {
    res.render('index', { name: 'Archer', age: '25' });
};

// Routes
app.get('/', home);

// different version
app.get('/', (req, res) => {
    res.send("<h1>This is the Home Page!</h1>");
});****
```
## node modules

many different kinds that assist in many different ways
must install and add to .gitignore so they don't upload to github
once installed you must import

```
npm i express // to install

const express = require('express'); // to import
const app = express();
```
### changing the script in the .JSON file will allow you to run the script from your terminal

```
scripts:

"start": "node app.js"
```

## setting up PORTS

Setting up a server using express 

```
const PORT = process.env.PORT || 8000;


app.listen(PORT, () => {
    console.log(`Server running on PORT:`, PORT);
});
```

## EJS and using javascript in EJS files

EJS allows you to attach a whole html page to render at set route
Using <%= %> (ice cream cones) to apply javaScript straight to html

```
<!DOCTYPE html>
<html>
  <head>
    <title>Home Page</title>
  </head>
  <body>
    <%- include('../partials/header.ejs') %> 

    <h1>Hello, <%= name %>!</h1>
    <% var dogAge = age*7 %>
    <h2>You are <%= dogAge %> in dog years.</h2>
    <% var status %>
    <%if (dogAge<100) {%>
      <% status = 'young' %>
    <%} else {%>
      <% status = 'old' %>
    <% } %>
    <h3>This means you are <%=status%>!</h3>
  </body>
</html>
```


## res.send

Essentially the console.log()
Not typically used in production

```
const input = (req, res) => {

    console.log(req.params);
    res.send(`My name is ${req.params.input}`);
}
```

## res.render

allows you to send an EJS (html) file to set route

```
const home = (req, res) => {
    res.render('index', { name: 'Archer', age: '25' });
};
```

## Module exporting

```
// destructuring
module.exports = {
    obj,
    array,
    isOldEnough,
    Player
};

// another way to export
module.exports.beBasic = () => "That's so fetch!"
module.exports.count = () => {
    for (var i = 0; i <= 10; i++) {
        console.log(i);
    }
}
```
### using destructuring method will have the export function locate at the bottom of your page. After the functions

## Module importing

```
const { beBasic, count } = require('./myModule.js');

const { obj, array, Player } = require('./myModule.js');
```

### Important to remember that whenever importing modules, it should be located at the top of your .js 
