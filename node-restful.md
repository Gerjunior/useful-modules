### # node-restful

node-restful module is used for automatizing http routes. With it in your project, you can simply declare a list of methods you want to use in a determinated model and it will make some default routes for yah!

## Installation

**npm**

```npm install node-restful```

**yarn** 
```yarn add express```

### Usage

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

For more details, visit the official  [node-restful documentation](https://github.com/baugarten/node-restful).