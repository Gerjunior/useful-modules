
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

After doing that, you can start the project using the command `nodemon <./filePath.js>` and everytime you save the file nodemon will take care of the execution.

For more details, visit the official [nodemon documentation](https://www.npmjs.com/package/nodemon).

### axios
Bored of used pure AJAX for assyncronously requests? Now you don't need it, so please say R.I.P to jQuery and stop using it! 

**Installation**
`npm install axios`

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


