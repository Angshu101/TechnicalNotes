---
title: DOM -Manupulation
created: '2023-07-01T22:33:32.887Z'
modified: '2023-07-02T06:21:27.630Z'
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
```
var a=document.getElementbyid("mainArea")--grabs the particular element with the div having same id name
a.innerHtml=Json.stringify(data)
vat b=document.createElement("div") 
 b.innerhtml="somrething"
 a.appenchild(b)
```

