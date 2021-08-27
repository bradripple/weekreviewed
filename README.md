# weekreviewed


## controllers and routes



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


```
npm i express // to install

const express = require('express'); // to import
const app = express();
```







