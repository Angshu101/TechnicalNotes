---
title: JavaScripts Concepts
created: '2023-06-30T20:04:03.309Z'
modified: '2023-07-02T00:49:27.935Z'
---

# JavaScripts Concepts

Difference Between JSON.strigify() & JSON.parse()

You would typically use JSON.stringify() when you want to convert a JavaScript object or value into a JSON string representation. This is useful when you need to transmit or store the data in a format that can be easily shared or used across different systems. For example, when sending data over a network or storing it in a database, you would often use JSON.stringify() to convert the data into a JSON string before sending or storing it.

Here's an example of using JSON.stringify()
```js
const data = {
  name: 'John',
  age: 25,
  city: 'New York'
};

const jsonString = JSON.stringify(data);
console.log(jsonString);

//output
//{"name":"John","age":25,"city":"New York"}
```
On the other hand, you would use JSON.parse() when you have a JSON string and want to convert it back into a JavaScript object or value. This is useful when receiving JSON data from an external source and need to work with it in your JavaScript code. JSON.parse() converts the JSON string into its corresponding JavaScript object or value.

Here's an example of using JSON.parse():
```js
const jsonString = '{"name":"John","age":25,"city":"New York"}';

const data = JSON.parse(jsonString);
console.log(data.name); // Output: John
console.log(data.age); // Output: 25
console.log(data.city); // Output: New York

```
* Use JSON.stringify() to convert a JavaScript object or value into a JSON string.
* Use JSON.parse() to convert a JSON string into a JavaScript object or valueś

Refer to this Link for DOM Manupulation Concepts
[[DOM -Manupulation]]
### Todo in file Server
In the below code learn the usage of the fs module and arrow function
app.get('/routes',()=>{}),
app.post('/routes',()=>{})
app.listen(portNumber,()=>{})
```js
const express = require('express');
const bodyParser = require('body-parser');
const fs = require("fs");

const app = express();

app.use(bodyParser.json());

function findIndex(arr, id) {
  for (let i = 0; i < arr.length; i++) {
    if (arr[i].id === id) return i;
  }
  return -1;
}

function removeAtIndex(arr, index) {
  let newArray = [];
  for (let i = 0; i < arr.length; i++) {
    if (i !== index) newArray.push(arr[i]);
  }
  return newArray;
}

app.get('/todos', (req, res) => {
  fs.readFile("todos.json", "utf8", (err, data) => {
    if (err) throw err;
    res.json(JSON.parse(data));
  });
});

app.get('/todos/:id', (req, res) => {
  fs.readFile("todos.json", "utf8", (err, data) => {
    if (err) throw err;
    const todos = JSON.parse(data);
    const todoIndex = findIndex(todos, parseInt(req.params.id));
    if (todoIndex === -1) {
      res.status(404).send();
    } else {
      res.json(todos[todoIndex]);
    }
  });
});

app.post('/todos', (req, res) => {
  const newTodo = {
    id: Math.floor(Math.random() * 1000000), // unique random id
    title: req.body.title,
    description: req.body.description
  };
  fs.readFile("todos.json", "utf8", (err, data) => {
    if (err) throw err;
    const todos = JSON.parse(data);
    todos.push(newTodo);
    fs.writeFile("todos.json", JSON.stringify(todos), (err) => {
      if (err) throw err;
      res.status(201).json(newTodo);
    });
  });
});

 app.put('/todos/:id', (req, res) => {
   fs.readFile("todos.json", "utf8", (err, data) => {
     if (err) throw err;
     const todos = JSON.parse(data);
    const todoIndex = findIndex(todos, parseInt(req.params.id));
     if (todoIndex === -1) {
       res.status(404).send();
     } else {
       const updatedTodo = {
         id: todos[todoIndex].id,
         title: req.body.title,
         description: req.body.description
       };
       todos[todoIndex] = updatedTodo;
       fs.writeFile("todos.json", JSON.stringify(todos), (err) => {
         if (err) throw err;
         res.status(200).json(updatedTodo);
       });
    }
   });
});

app.delete('/todos/:id', (req, res) => {

  fs.readFile("todos.json", "utf8", (err, data) => {
    if (err) throw err;
    const todos = JSON.parse(data);
    const todoIndex = findIndex(todos, parseInt(req.params.id));
    if (todoIndex === -1) {
      res.status(404).send();
    } else {
      todos = removeAtIndex(todos, todoIndex);
      fs.writeFile("todos.json", JSON.stringify(todos), (err) => {
        if (err) throw err;
        res.status(200).send();
      });
    }
  });
});

// for all other routes, return 404
app.use((req, res, next) => {
  res.status(404).send();
});

module.exports = app;

```

![[Pasted image 20230705015016.png]]
short cut of pusing vDom element to existingDOM