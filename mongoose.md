# mongoose

Official MongoDB driver! 

## Installation 
**npm**

```npm install mongoose```

**yarn**

```yarn add mongoose```

```js
const mongoose =  require('mongoose')

module.exports  = mongoose.connect('mongodb+srv://<user>:<login>@<password>@cluster0-nfnvf.mongodb.net/<collectionName>?retryWrites=true&w=majority', {
	useNewUrlParser:  true,
	useUnifiedTopology:  true,
	useFindAndModify:  true

})

```

>Ps: MongoDB Atlas is a global cloud database service that you can use to host your data. You have one free server to begin with.

