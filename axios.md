# axios 

Bored of used pure AJAX for assyncronously requests? Now you don't need it, so please say R.I.P to jQuery and stop using it!

## Installation  
`npm install axios`  
**or**
`yarn add global axios`

**Example**

> Using GitHub api

```
const axios = require('axios');

async getInformation(request,response) {
	const { github_username } = request.body;
	
	const apiResponse = await axios.get(`https://api.github.com/users/${github_username}`);
    const { name = login, bio, avatar_url } = apiResponse.data;

	...
}

```

Click here to see the official docs  [axios documentation](https://github.com/axios/axios).