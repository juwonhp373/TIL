# JavaScript 기초6
## Object.keys();
returns an array of keys.
```js
var arr = ['a', 'b', 'c'];
console.log(Object.keys(arr));
// console: ['0', '1', '2']

// array like object
var obj = { 0: 'a', 1: 'b', 2: 'c' };
console.log(Object.keys(obj));
// console: ['0', '1', '2']

// array like object with random key ordering
var anObj = { 100: 'a', 2: 'b', 7: 'c' };
console.log(Object.keys(anObj));
// ['2', '7', '100']

// getFoo is property which isn't enumerable
var myObj = Object.create({}, {
  getFoo: {
    value: function () { return this.foo; }
  } 
});
myObj.foo = 1;
console.log(Object.keys(myObj));
// console: ['foo']
```
```js
var person = {  
  name: 'juwon',  
  gender: 'female'  
};  
  
var people = [  
  {  
    gender: 'male',  
  items: [  
      {  
        name: 'kyle'  
  }  
    ]  
  },  
  {  
    gender: 'female',  
  items: [  
      {  
        name: 'amy'  
  },  
  {  
        name: 'juwon'  
  }  
    ]  
  }  
]  
  
console.log(person.name, person.gender);  
//juwon female  
  
var key1 = 'name';  
var key2 = 'gender';  
console.log(person[key1], person[key2]);  
//juwon female  
  
for(var key in person) {  
  console.log(key + ' => ' + person[key]);  
};  
// name => juwon  
// gender => female  
  
var length = Object.keys(person).length;  
console.log(length);  
// 2  
  
var lengths = Object.keys(people).length;  
console.log(people[1][Object.keys(people[1])[0]]);  
// female  
console.log(people[1][Object.keys(people[1])[1]]);  
// [ { name: 'amy' }, { name: 'juwon' } ]
```
## Object.values();
returns an array of values.
```js
const object1 = {
	a: 'something',
	b: 42,
	c: false
};
console.log(Object.values(object1));
// [ 'something', 42, false ]
```
## Object.entries();
returns an array of [key, value] pairs.
```js
let user = {
  name: "John",
  age: 30
};
console.log(Object.entries(user));
//[ [ 'name', 'John' ], [ 'age', 30 ] ]
```
