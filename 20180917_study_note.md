# 실습
### 새로운 page 만드는 법
page 안에 'component-test.vue' 를 만든다.

router 의 'index.js' 에
```js
import Vue from 'vue';  
import Router from 'vue-router';  
import Hello from '../page/Hello';  
import Test from '../page/component-test';  
  
Vue.use(Router);  
  
export default new Router({  
  mode: 'history',  
  routes: [  
 {  path: '/vue-router-sample2',  
  name: 'Hello',  
  component: Hello  
    },  
 {  path: '/vue-router-sample2/component-test',  
  name: 'component-test',  
  component: Test  
    }  
 ]});
```
> routes 안에  새로운 페이지를 정의해 준다.


### Component 만들고 App.vue 에 선언하는 법
'Components' 안에 'test.vue' 파일을 생성한다.
```js
<script>  
export default {  
  name: 'test'  
};  
</script>
```
> 라고 형성이 된다.

'vuex' 안에 있는 'App.vue' 
```js
<script>  
import Vue from 'vue';  
import { store } from './vuex/store';    
import test from './components/test';  

Vue.component(test.name, test);  
  
export default {  
  name: 'App',  
  store,  
  methods: {}  
};  
</script>
```

이제 page 로 가서 화면에 컴포넌트를 적용해 볼 것이다.
```html
<template>  
 <div class="hello">  
  <test></test>
 </div>
</template>
```
> 이런식으로 적용 하면 화면에 test 컴포넌트가 뜨게 된다.

### 새로 만든 'component-test.vue' page 에서 	component 로 만든 'vue-dialog.vue' 를 가져와서 띄우는 법.

**'vue-dialog.vue'** 에서 어떠한 특정한 버튼을 누르면 dialog 가 뜨고, dialog 가 뜬 후에는 'delete' 나 'ignore' 을 누르면 dialog 가 꺼지게 한다.

```pug
<template lang="pug">  
  .dialog-zone.flex(v-if="active")  
   .dialog-field.flex  
    .title-grid.flex.align-center 데이터 삭제  
    .context-grid.flex.  
        현재 선택한 [메리네툭스 카드] 가 삭제됩니다. <br> 정말 데이터를 삭제하시겠습니까?  
    .button-grid.flex.align-center  
     .button-cell.flex.align-center(v-on:click="close") delete  
     .button-cell.flex.align-center(v-on:click="close") ignore  
  
</template>  
```
> `v-if` 가 true 이면 화면에 보이고, false 이면 화면에 보이지 않는다.
> `v-on` click, 눌렀을 때, "close" 라는 함수를 불러온다.
```js
<script>  
export default {  
  name: 'vue-dialog',  
  data() {  
  return {  
  active: false  
  };  
 },  methods: {  
  open() {  
  this.active = true;  
 },  close() {  
  this.active = false;  
 } }};  
</script>
```
> 처음에는 dialog 가 화면에 보이지 않도록 하고,

> 나중에 page 에 적용될 때, page 에 있는 버튼을 누르면 dialog 가 화면에 뜨게 해야한다. 

> 또한 dialog 가 띄워졌을때, dialog 의 두개의 버튼 중 아무거나 누르게 되어도 dialog 가 화면에서 사라져야한다.

> dialog 를 하나의 기능으로 만들어서 아무 페이지 에서 들고와도 똑같은 방법으로 사용할 수 있게 해야하기 때문에 기능에 대한 함수는 component 자체에 정의 되어있어야 한다.

**`component-test.vue`** 에서
```pug
<template lang="pug">  
  .zone  
   .open-dialog-button.flex.align-center(v-on:click="openDialog") Open Dialog  
   vue-dialog(ref="defaultDialog")  
</template>  
```
> `v-on:click="openDialog"`
> -> 이 버튼을 눌렀을 때, "openDialog" 라는 함수를 불러온다.

> `vue-dialog(ref="defaultDialog")`
> -> "defaultDialog" 가 'vue-dialog' 를 가르키고 있다는 것이다.
```js
<script>  
export default {  
  name: 'component-test',  
  methods: {  
  openDialog() {  
  this.$refs.defaultDialog.open();  
  console.log('click=Button');  
 }
  }
   };  
</script>
```
> `$refs`
> -> ref 로 변수가 가르키는 것을 정한다.
> 버튼이 위와 다르게 여러개 일때 ref 는 더 많을 것이다.  그런 ref 들을 모아둔 것이 **$refs** 이다.

> pug 에서 버튼을 누름으로 불러온 함수 openDialog 에서는, this 에 있는 `$refs` 의 설정해둔 'vue-dialog' 를 가르키고 있는 'defaultDialog' 에서 'open()' 이란 함수를 가져온 것이다.

> 이는 `(v-on:click="openDialog")` 을 true 로 바꿔서 화면에 	보이게 만들 것이다.