### [](https://github.com/Gerjunior/useful-modules#axios)axios

Bored of used pure AJAX for assyncronously requests? Now you don't need it, so please say R.I.P to jQuery and stop using it!

**Installation**  
`npm install axios`  
**or**
`yarn add global axios`

**Usage**

> Using GitHub api

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

For more details, visit the official  [axios documentation](https://github.com/axios/axios).