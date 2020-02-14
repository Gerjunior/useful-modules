### [](https://github.com/Gerjunior/useful-modules#express)express

There are a lot of functionalities in  **express**, but the most used (and the one I will show here) is the routing one. You can easily open a localhost server for testing your app using this module.

**Installation**
  `npm install express`  
  **or** 
   `yarn add express`
   
**Usage**

```
const  express = require('express')

const app = express();

//GET route, which will show the message "Hello, World!".
app.get('/', (req, res) => {
	res.send('Hello, World!')
	})

//Starting the localhost server on port 3000. 
//Use 'localhost:3000' to access.
app.listen(3000, () => {
	console.log('Listening on port 3000.')
	})

```

***Using express-generator***
**Start a fresh project**.  You can use  **express-generator**  to start a new express project from an existing template.  **Install**  using  `npm install express-generator -g`  or  `yarn add global express-generator`.

```
Starting a new Project.

Usage: express [options][dir]
  Options:
    -h, --help          output usage information
        --version       output the version number
    -e, --ejs           add ejs engine support
        --hbs           add handlebars engine support
        --pug           add pug engine support
    -H, --hogan         add hogan.js engine support
        --no-view       generate without view engine
    -v, --view <engine> add view <engine> support (ejs|hbs|hjs|jade|pug|twig|vash) (defaults to jade)
    -c, --css <engine>  add stylesheet <engine> support (less|stylus|compass|sass) (defaults to plain css)
        --git           add .gitignore
    -f, --force         force on non-empty directory

in this example we will use an app named [ FreshStart ]

Creation: express --view=pug FreshStart
   Debug: 
     cd FreshStart
     npm install or yarn add
     set DEBUG=myapp:* & npm start [Note: If you used yarn to install packages start with yarn start]

```


For more details, visit the official  [express documentation](https://expressjs.com/pt-br/starter/installing.html).