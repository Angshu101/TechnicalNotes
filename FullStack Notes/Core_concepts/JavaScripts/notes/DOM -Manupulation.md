---
title: DOM -Manupulation
created: '2023-07-01T22:33:32.887Z'
modified: '2023-07-01T22:51:11.181Z'
---

# DOM -Manupulation 

## fetch() Command

```js
const todoData = {
  title: 'New Todo',
  completed: false
};

const requestOptions = {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify(todoData)
};

fetch('http://localhost:3000/todos', requestOptions)
  .then(response => response.json())
  .then(data => {
    console.log(data);
  })
  .catch(error => {
    console.log('Error:', error);
  });
//Here we are Sending a post request to the backend using the browser here the requestOptions can be written directly inside fetch
```
