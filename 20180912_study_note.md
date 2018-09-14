### v-for
> 배열의 데이터를 사용해 항목 목록을 표시하는데 사용할 수 있다.

#### HTML 의 `<ol>` 요소 (HTML Ordered List Element)
-> 정렬된 리스트의 항목들을 나타낸다.
-> 일반적으로 정렬된 리스트의 항목들은 앞에 번호와 함께 표시되며, 이 번호는 숫자, 문자, 로마 숫자, 점과 같이 어떤 형태로든 나타낼 수 있다.

#### `<ol>` 과 `<ul>` 은 둘다 아이템의 리스트를 나타낸다.
`<ol>` 
-> 순서가 의미가 있다.
-> 규칙을 결정하기 위해 목록 항목의 순서를 변경하는것이 의미가 있다.

`<ul>` (HTML Unordered List)
-> 리스트에서 순서가 의미 없는, 숫자 순서를 가지고 있지 않은, 정렬되지 않은 항목들의 리스트를 나타낸다.
-> 정렬되지 않은 리스트의 항목들은 굵은 점과 함께 표시된다.

```html
<template>
<div class="hello">
  <ol>  
   <li v-for="todo in todos">  
    {{ todo.text }}  
    </li>  
  </ol>
```
```js
<script>  
  
import { store } from '../vuex/store';  
  
export default {  
  name: 'HelloWorld',  
  store,  
  data() {  
  return {  
  msg: 'Welcome to Hanu Vue Template',  
  posX: 0,  
  posY: 0,  
  name: 'Juwon',  
  message: `이 페이지는 ${new Date()} 에 로드 되었습니다.`,  
  seen: true,
  // 여기에 추가한다.
  todos: [  
 { text: 'JavaScript 배우기' },  
 { text: 'Vue 배우기' },  
 { text: 'HTML 배우기' }  
 ] 
 }; 
 },
```
> 아래와 같이 떠야 한다.
> 1. JavaScript 배우기
> 2. Vue 배우기
> 3. HTML 배우기

> 하지만 이렇게 했는데 아래와 같이 한줄에 뜬다.
> JavaScript 배우기 Vue 배우기 HTML 배우기
> 왜_???