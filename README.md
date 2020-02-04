
# useful-modules
This is intented to be a quick guide to the most used and useful modules for building applications in NodeJS, ReactJS and other future frameworks that I will use for front-end development.
Before starting, be sure to have **NodeJS** and **npm** installed on your local machine. You can also use **yarn** for package managing.
After that, open your project and do a `npm init` or `yarn init` to start you package manager.
*PS : On this first template, I will only write commands using **npm** to facilitate.* 

## NodeJS libraries

NodeJS is a back-end Javascript, one of the most used languages in the ***[Omnistack](https://medium.com/@cesar.will.hilario/omnistack-um-desenvolvedor-javascript-omnipresente-por-c%C3%A9sar-hil%C3%A1rio-3ce29d280bf8)***.

### nodemon

Nodemon is used to turn our lives as developers easier, restarting the *.js* file automatically before saving.

**Installation**
***Global*** :`npm install -g nodemon`
***Local***: `npm install --save-dev nodemon`

**Or you can use Yarn**
***Global*** : `yarn add global nodemon`
***Local*** : `yarn add nodemon`

After doing that, you can start the project using the command `nodemon <./filePath.js>` and everytime you save the file nodemon will take care of the execution.

For more details, visit the official [nodemon documentation](https://www.npmjs.com/package/nodemon).

### axios
Bored of used pure AJAX for assyncronously requests? Now you don't need it, so please say R.I.P to jQuery and stop using it! 

**Installation**
`npm install axios`
**Or you can use Yarn**
***Local*** : `yarn add global axios`

**Usage**
>Using GitHub api
```
const axios = require('axios');
//Importation

async getInformation(request,response) {
	
	const { github_username } = request.body;
	//Getting the github_username variable from the requisition body
	
	const apiResponse = await axios.get(`https://api.github.com/users/${github_username}`);
	//Using axios to access the GitHub api
    
    const { name = login, bio, avatar_url } = apiResponse.data;

	...
}
```

For more details, visit the official [axios documentation](https://github.com/axios/axios).
### express

There are a lot of functionalities in **express**, but the most used (and the one I will show here) is the routing one. 
You can easily open a localhost server for testing your app using this module.

**Installation**
`npm install express`
**Or you can use Yarn**
***Local*** : `yarn add express`

**Start a fresh project**
You can use **express-generator** to start a new express project from an existing template.
**install** using `npm install express-generator -g` or if you want to use Yarn `yarn add global express-generator`
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
For more details, visit the official [express documentation](https://expressjs.com/pt-br/starter/installing.html).

### node-restful

node-restful module is used for automatizing http routes. With it in your project, you can simply declare a list of methods you want to use in a determinated model and it will make some default routes for yah!

**Instalation**
`npm install node-restful`
**Or you can use Yarn**
***Local*** : `yarn add express`

**Usage**
On TODO model file 
> Using mongoose

```
const restful = require('node-restful')
const mongoose = restful.mongoose

const todoSchema = new mongoose.Schema({
    description: { type: String, required: true },
    done: { type: Boolean, required: true, default: false},
    createdAt: { type: Date, default: Date.now}
})

module.exports = restful.model('Todo', todoSchema)
```
On todoService
```
const Todo = require('./todo')

Todo.methods(['get', 'post', 'put', 'delete']);
Todo.updateOptions({new: true, runValidators: true})

module.exports = Todo
```
On routes.js
> Using express
```
const express = require('express')

module.exports = (server) => {

    const router = express.Router()
    server.use('/api', router)

    const todoService = require('../api/todo/todoService')
    todoService.register(router, '/todos')
    
}
```
For more details, visit the official [node-restful documentation](https://github.com/baugarten/node-restful).

### Nest Js

NestJs is a progressive Node.js framework for building efficient and scalable server-side applications.

**Instalation**
`npm i -g @nestjs/cli`
**Or you can use Yarn**
***Local*** : `yarn add global @nestjs/cli`

**Usage**
create the project
> nest new FreshStart

Main.ts
```
import { NestFactory } from '@nestjs/core';
import { AppModule } from './app.module';

async function bootstrap() {
  const app = await NestFactory.create(AppModule);
  await app.listen(3000);
}
bootstrap();
```
For more details, visit the official [NestJs documentation](https://docs.nestjs.com/first-steps).


