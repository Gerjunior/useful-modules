# express

Easily create REST APIs.

**Installation**
  `npm install express`  
  **or** 
   `yarn add express`

**Usage**

```js
const  express = require('express')

const app = express();

//GET route, which will show the message "Hello, World!".
app.get('/', (req, res) => {
	res.send('Hello, World!')
	})

//Starting the localhost server. 
//Use 'http://localhost:3333' to access.
app.listen(3333, () => {
	console.log('Listening on port 3333.')
	})

```


For more details, visit the official [express documentation](https://expressjs.com/pt-br/starter/installing.html).