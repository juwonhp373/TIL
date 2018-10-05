# Vuex 기초 2.
**[Vuex 기초 1.](https://github.com/juwonhp373/TIL/blob/master/20181001_study_note.md) 에서 보였듯이 마지막 방법도 문제가 있다.**

자식 컴포넌트들의 계층 구조가 복잡해지면 일일이 부모 컴포넌트에 지정된 정보를 계층 구조를 따라 props로 전달해주어야 한다.
유지보수 중에 새로운 상태 정보가 추가되면(data 옵션 객체에 정보가 추가되면) 최종 자식 컴포넌트까지 전달되는 경로에 있는 모든 컴포넌트들의 props 옵션이 모두 변경될 것이다.

따라서 최종적으로 생각해볼 수 있는 방법이 전역 객체를 하나 만들어서 각 컴포넌트에서 참조하여 사용하는 방법이다.
![](https://steemitimages.com/0x0/https://github.com/stepanowon/vuejs_book/blob/master/vuex/vuex_images/vuex03.jpg?raw=true)

앞의 그림에서 Global 상태 정보 객체는 단순하게 정보를 담은 객체이다.
```js
export default { 
	name : "이몽룡", 
	scores : [ 
		{ course : "국어", score: 100 }, 
		{ course : "수학", score: 90 }, 
		.. ] 
}
```
이러한 전역 상태 정보 객체를 각 컴포넌트에서는 다음과 같이 참조해서 사용 할 수 있다.

[UIComponent.vue]
```js
<script type="text/javascript"> 
import globalState from './globalState.js' 
export default { 
	name : "ui-component", 
	data : function() { 
		return globalState 
	}, 
	... 
} 
</script>
```
이렇게 하면 모든 컴포넌트들이 동일한 상태정보를 공유할 수 있다.

한 컴포넌트에서 데이터를 변경하면 전역 상태가 변경될 것이다. (객체는 참조형이니까)

**하지만 이 방법도 문제가 있다!**

Vue 는 데이터(상태) 를 중심으로 움직인다.
MVVM 모델이기 때문에 상태(데이터) 가  바뀌면 ViewModel 객체가  바라보고 있다가 감지하여 UI 를 자동으로 변경한다.
이렇게 중요한 상태 데이터가 어느 컴포넌트, 어떤 메소드에 의하여 언제 변경 됐는지 전혀 알 수 없게된다.

**그렇기 때문에 Vuex 같은 상태관리 라이브러리를 사용하는 것이다!!!**

- 중앙 집중화된 상태 정보 관리가 필요하다.
- 상태 정보가 변경되는 상황과 시간을 추적하고싶다.
- 컴포넌트에서 상태 정보를 안전하게 접근하고 싶다.

![Vuex architecture](https://steemitimages.com/0x0/https://github.com/stepanowon/vuejs_book/blob/master/vuex/vuex_images/vuex04.jpg?raw=true)
화살표가 한방향으로 흐르는 것을 보고 '단방향 데이터 흐름', '단방향 데이터 바인딩' 이라는 용어를 쓴다.

- 컴포넌트가 액션을 일으키면 (ex 버튼 클릭)
- 액션에서는 외부 API 를 호출한 뒤 그 결과를 이용해 변이를 일으키고(if 외부 API 가 없으면 생략)
- 변이에서는 액션의 결과를 받아 상태를 변경한다. 이과정은 추적이 가능해서 DevTools 와 같은 도구를 이용하면 상태 변경의 내역을 모두 확인할 수 있다.
- 변이에 의해 변경된 상태는 다시 컴포넌트에 바인딩되어 UI 를 갱신한다.