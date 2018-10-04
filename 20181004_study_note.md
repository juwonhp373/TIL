## animation


## v-bind
```html
<div v-bind:class="{ active: isActive }"></div>
```
`active` 클래스의 존재 여부가 데이터 속성 `isActive`	의 **참 속성**에 의해 결정되는 것을 의미한다.
```html
<div class="static" v-bind:class="{ active: isActive, 'text-danger': hasError }">
</div>
```
그리고 데이터는:
```js
data: {  
 isActive: true,  
 hasError: false  
}
``` 
그러면 아래와 같이 렌더링 된다:
```html
<div class="static active"></div>
```
------
- 바인딩 된 객체는 인라인일 필요는 없다.
```html
<div v-bind:class="classObject"></div>
```
```js
data: {  
 classObject: {  
 active: true,  
 'text-danger': false  
 }  
}
```
> 같은 결과로 렌더링 된다.
------
- 계산된 속성에도 바인딩 할 수 있다.
```html
<div v-bind:class="classObject"></div>
```
```js
data: {  
 isActive: true,  
 error: null  
},  
computed: {  
 classObject: function () {  
	 return {  
		 active: this.isActive && !this.error,  
		 'text-danger': this.error && this.error.type === 'fatal'  
  }  
 }  
}
```

### v-model vs v-bind
- `v-model` 은 데이터를 동적으로 바인딩 할 때 사용
(`<input v-model="message">` 와 같이 작성하면 실시간으로 `message` 라는 데이터의 값을 변경할 수 있음)
- `v-bind` 는 속성을 표현식에 동적으로 바인딩 할 때 사용
축약형으로 `:` 로 대체 가능
( `<img:src="img.jpg">` 와 같이 작성하면 이미지의 주소를 불러옴) 


## HTML class 속성
### class 속성
```html
<style type="text/css">

.hello{
color:  red;
}

</style>

<span class="hello">안녕하세요.</span>
```
class 속성은 아이디(id) 속성과 같이 모든 요소에 사용 가능한 속성이다.

class 이름은 한 요소에 여러 개를 넣을 수 있다. 값은 띄어쓰기로 구분한다.

```html
<div class="hello test">Hello World</div>
```
### div는 블럭 요소이고, span 은 인라인 요소이다.
둘다 자기자신을 중첩할 수 있다.

`<div>` 태그와 `<span>` 의 차이점은 `display` 속성이 `block` 이 아닌,  `inline` 이다.

`<div>` 는 줄바꿈이 되지만, `<span>` 은 줄바꿈이 되지 않는다.

```html
<div>
	<span style="background-color:red">span1</span>
	<span style="background-color:blue">span2</span>
	<span style="background-color:green">span3</span>
</div>
```
![span](https://i.postimg.cc/jqBwLf3k/2018-10-04_4.01.59.png)

```html
<div>
	<div style="background-color:red">span1</div>
	<div style="background-color:blue">span2</div>
	<div style="background-color:green">span3</div>
</div>
```
![div](https://i.postimg.cc/44YHfPP9/2018-10-04_4.01.32.png)




