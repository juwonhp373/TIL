# 시작하기
## Vue.js 란?
- 가상 DOM 을 사용한다.
- 데이터와 DOM 이 연결되어 모든것이 반응형이다.
- 컴포넌트를 제공한다.
- 뷰에만 집중하고 있고, 라우터, 상태관리를 위해선 써드파티 라이브러리를 사용한다.
- React 에서는 JSX 를 사용하고 있듯이 Vue 에서는 템플릿(template) 을 사용하고 있다.
- 스트리밍 서버사이드 렌더링이 지원된다
-> 이벤트 루프가 막히지 않는다.
-> 따라서 유저들에게 더 빠르게 결과를 반환 할 수 있다.

# 선언적 렌더링
## Hello.vue
> 'Hello.vue' 코드를 변경해서 vue 사용법을 알아본다.

처음 'vue-router-sample2' 프로젝트를 생성하고 바로 
'http://localhost:8082/vue-router-sample2' 로 들어가면,
**"Welcom to Hanu Vue Template"**
이라고 뜨는 화면을 확인 할 수 있을것이다.
여기서 **Hanu** 대신에 다른 값이 들어가게 뷰를 정의 하려면 

'Hello.vue' 에서 아래처럼 바꾸면 된다.
```html
<template>  
 <h1>Welcome to {{ name }} Vue Template</h1>
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
  // 여기에 추가한다.
  name: 'Juwon'  
  };  
 },
```
## 디렉티브
Vue에서 제공하는 특수 속성임을 나타내는 `v-` 접두어가 붙어있으며 렌더링 된 DOM 에 특수한 반응형 동작을 한다.

### v-bind
`title` 속성을 Vue 인스턴스의 `message` 속성으로 최신상태를 유지한다.

```html
<template>  
 <span v-bind:title="message">  
  내 위에 잠시 마우스를 올리면 동적으로 바인딩 된 title을 볼 수 있습니다!  
    </span>
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
  // 여기에 추가한다.  
  message: `이 페이지는 ${new Date()} 에 로드 되었습니다.`};  
 },
```
> 'message: ' 에 string을 쓸때,  안에 변수가 있는 경우에는 `` 를 사용하여 묶는다.

> 이때, `` 안의  변수는 `${ }` 안에 넣는다.

# 조건문과 반복문
엘리먼트의 존재 여부를 토글하는 것

```html
<template>   
 <p v-if="seen">이제 나를 볼 수 있어요</p>
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
  // 여기에 추가한다.
  seen: true  
  };  
 },
```
> `seen: false` -> 메세지가 사라진다.

- 이 예제는 텍스트와 속성 뿐만 아니라  DOM 의 구조에도 데이터를 바인딩 할 수 있음을 보여준다.
- Vue 엘리먼트가 Vue에 삽입/ 갱신/ 제거될 때 자동으로 **트랜지션 효과**를 적용할 수 있는 시스템 제공한다 .
