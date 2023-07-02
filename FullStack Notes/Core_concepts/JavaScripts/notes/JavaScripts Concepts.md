---
title: JavaScripts Concepts
created: '2023-06-30T20:04:03.309Z'
modified: '2023-07-02T00:15:09.727Z'
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


