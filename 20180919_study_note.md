### 예외 Object.freeze ()
```js
var obj = {
	foo: 'bar'
}

Object.freeze(obj)

new Vue({
	el: '#app',
	data: obj
})
```
```html
<div id="app">
	<p>{{ foo }}</p>
	<!-- obj.foo 는 더이상 변하지 않습니다! -->
	<button v-on:click="foo = 'baz'">Change it</button>
</div>
```
>  실제 Vue 에서 어떻게 쓰였는지 해보고 싶은데 방법을 잘 모르겠다_???

### Vue 인스턴스의 데이터 속성 이외의 속성
Vue 인스턴스는 데이터 속성 이외에도 유용한 인스턴스 속성 및 메소드를 제공한다.

다른 사용자 정의 속성과 구분하기 위해 접두어 `$` 를 붙인다.

ex)
```js
var data = { a: 1 }
var vm = new Vue({
	el: '#example',
	data: data
})

vm.$data === data // => true
vm.$el === document.getElementById('example') // => true

// $watch 는 인스턴스 메소드 입니다.
vm.$watch('a', function (newVal, oldVal) {
	// 'vm.a' 가 변경되면 호출된다.
})
```
> 밖에 있는 	`data` 랑 `vm` 안에 있는 `data` 를 구분하기 위해 `$` 를 붙인다.
> 다른것도 마찬가지

# 인스턴스 라이프사이클 훅
각 Vue 인스턴스는 데이터 관찰을 설정하고,
템플릿을 컴파일하고,
인스턴스를 DOM 에 마운트 하고,
데이터가 변경될 때 DOM 을 업데이트해야 할 때 **초기화 단계**를 거친다.

그 과정에서 사용자 정의 로직을 실행할 수 있는 **라이프사이클 훅** 도 호출된다.

ex)
`created` 훅은 인스턴스가 생성된 후에 호출된다.
```js
new Vue({
	data: {
		a: 1
	},
	created: function () {
		console.log('a is: ' + this.a)
	}
})
// => "a is: 1"
```

인스턴스 라이프사이클의 여러 단계에서 호출될 다른 훅도 있다.
ex) `mounted` , `updated` , `destroyed` 

모든 라이프사이클 훅은 `this` 컨텍스트가 호출하는 Vue 인스턴스를 가리키며 호출된다.

Vue 세계에서 **"컨트롤러"** 는 없다.
컴포넌트의 사용자 지정 로직은 이러한 라이프사이클 훅으로 분할된다.

### !!!주의!!!
options 속성이나 콜백에
```js
created: () => console.log(this.a)
```
or
```js
vm.$watch('a', newValue => this.myMethod())
```
> 위, 둘과 같은 **화살표 함수** 사용을 안하는게 좋다. 

> 화살표 함수들은 	부모 컨텍스트에 바인딩되기 때문에, `this` 컨텍스트가 호출하는 Vue 인스턴스에서 사용할 경우, 

```js
Uncaught TypeError: Cannot read property of undefined
```
or
```js
Uncaught TypeError: this.myMethod is not a function
```
> 위, 둘과 같은 오류가 발생하게 된다.