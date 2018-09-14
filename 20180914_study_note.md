# 사용자 입력 핸들링

### v-on
사용자가 앱과 상호 작용할 수 있게 하기 위해 v-on 디렉티브를 사용하여 Vue 인스턴스에 메소드를 호출하는 이벤트 리스너를 첨부 할 수 있다.

```html
<template>  
 <div class="hello">
	<p>{{ message }}</p>  
	<button v-on:click="reverseMessage">메시지 뒤집기</button>
 </div>
</template>
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
  // 메세지 여기에 추가
  message: '안녕하세요! Vue.js!'
  };
   },
 methods: {  
  increment() {  
  this.$store.commit('increment', { inc: 1 });  
 },  decrement() {  
  this.$store.commit('increment', { inc: -1 });  
 },  async mousemoved() {  
  console.log(this);  
 },  reverseMessage() {  
  this.message = this.message.split('').reverse().join('');  
 } // reverseMessage(){} 추가.
  }
  };
```
> '메시지 뒤집기' 버튼을 누르면
> '안녕하세요! Vue.js!' -> '!sj.euV !요세하녕안' 
> 으로 바뀐다.

DOM 을 건드리지 않고 앱의 상태를 업데이트한다.
모든 DOM 조작은 Vue 에 의해 처리되며 작성한 코드는 기본 로직에만 초점을 맞춘다.

### v-model
양식에 대한 입력과 앱 상태를 양방향으로 바인딩 하는 v-model 디렉티브를 제공한다.

```html
<template>  
 <div class="hello">
  <p>{{ message }}</p>  
  <input v-model="message">
 </div>
</template>
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
  // 메세지 여기에 추가
  message: '안녕하세요! Vue.js!'
  };
   },
```
>  아래에 input 창에 글을 다른거로 바꾸면 그게 바로 반영되어 글씨가 	바뀐다.

# 컴포넌트를 사용한 작성방법
컴포넌트 시스템은 Vue 의 중요한 개념이다.

작지만 그 자체로 제 기능을 하며 재사용 할 수 있는 컴포넌트로 구성된 대규모 응용 프로그램을 구축할 수 있게 해주는 추상적 개념이다.

![거의 모든 유형의 응용 프로그램 인터페이스를 컴포넌트 트리로 추상화할 수 있다.](https://kr.vuejs.org/images/components.png)

Vue 에서의 컴포넌트는 본질적으로 **미리 정의된 옵션을 가진 Vue 인스턴스** 이다.

```html
<template>  
 <div class="hello">
  <template-change></template-change>
 </div>
</template>
```
```js
<script>  
  
// vue 를 Vue 라고 하고 사용하겠다.
import Vue from 'vue';  
import { store } from '../vuex/store';    
  
Vue.component('template-change', {  
  template: '<li>할일 항목 하나입니다.</li>'  
});
```
> html 에서 'template-change' 를 넣은 부분에 컴포넌트가 들어간다.
-> 할일 항목 하나입니다.

위는 모든 'template-change' 인스턴스에 똑같은 내용을 렌더링 할 것이다.

부모영역의 데이터를 자식 컴포넌트에 집어넣을 수 있어야 한다.

**prop** 을 전달 받을 수 있도록 'template-change' 컴포넌트의 정의를 수정한다.

### prop
```html
<template>  
 <div class="hello">
  <ol>
  <!--
	  이제 각 template-change 에 todo 객체를 제공한다.
	  화면에 나오므로, 각 항목의 컨텐츠는 동적으로 바뀔 수 있다_???
	  또한 각 구성요소에 "키"를 제공해야한다_??? (나중에 설명 된다고 한다.)
  -->
   <template-change  
    v-for="item in groceryList"  
    v-bind:todo="item"  
    v-bind:key="item.id">  
   </template-change>  
  </ol>
 </div>
</template>
```
```js
<script>  
  
import Vue from 'vue';  

Vue.component('template-change', {  
  // template-change 컴포넌트는 "prop" 이라고 하는 사용자 정의 속성 같은 것을 입력 받을 수 있다.
  //이 prop 은  todo	라는 이름으로 정의했다.
  props: ['todo'],  
  template: '<li>{{ todo.text }}</li>'  
});  
  
export default {  
  name: 'HelloWorld',  
  store,  
  data() {  
  return {  
 groceryList: [  
 { id: 0, text: 'Vegetables' },  
 { id: 1, text: 'Cheese' },  
 { id: 2, text: 'Whatever else humans are supposed to eat' }  
 ]
  };
   },
```
> 1. Vegetables
> 2. Cheese
> 3. Whatever else humans are supposed to eat

자식을 props 인터페이스를 통하여 부모로부터 분리 할 수 있었다.

앞으로 부모 앱에 영향을 주지 않으면서 <template-change> 컴포넌트를 더 복잡한 템플릿과 로직으로 더욱 향상 시킬 수 있어야 한다.

대규모 응용 프로그램에서는 개발 과정을 관리할 수 있는 수준 하에 두기 위해 전체 앱을 컴포넌트로 나누는 것이 필수적이다.

ex)
```html
<div id="app">  
	<app-nav></app-nav>  
	<app-view>  
		<app-sidebar></app-sidebar>  
		<app-content></app-content>  
	</app-view>  
</div>
```
