# #TypeScript 변수 선언
## 변수 선언
`let` 은 어떤면에서는 	`var`와 유사하지만 사용자가 JavaScript 로 실행하는 일반적인 “gotchas” 를 피할 수 있다.
`const` 는 변수에 재할당하는 것을 막는다는 점에서 `let` 을 보완한 것이다.

TypeScript 가 JavaScript 의 상위 집합체이기 때문에 당연히 `let` 과 `const` 를 지원한다.
`var` 선언자보다 바람직하다.

함수 내부의 다른 함수(중첩함수) 에서 변수에 엑세스 할 수 있다.

```typescript
function f() {
	var a = 10;
	return function g() {
		var b = a + 1;
		return b;
	}
}

var g = f();
g(); // returns '11'
```

```typescript
function f() {
	var a = 1;
	a = 2;
	var b = g();
	a = 3;

	return b;
	
	function g() {
		return a;
	}
}

f(); // returns '2'
```

> ???????????????????

## Scope 규칙
```typescript
function f(shouldInitialize: boolean) {
	if (shouldInitialize) {
		var x = 10;
	}
	return x;
}

f(true); // returns '10'
f(false); // returns 'undefined'
```

위 코드에서 변수 `x` 는 `if` 블록 내에서 선언되었지만 그 블록 외부에서 변수에 접근할 수 있다.
왜냐하면 `var` 선언은 포함 함수, 모듈, 네임 스페이스 또는 전역 범위 (모든 요소는 포함된 블록에 관계없이) 에서 액세스 할 수 있다.
이러한 방식을 `var` /- scoping/ 또는 /Function-scoping/ 이라고 표현한다.
함수의 parameter 도 function scope 이다.



### 모듈(module)
기본적으로 본체에 대한 독립된 하위단위라는 필연적인 개념의 큰 틀을 따르고 있다.
일반적으로 큰 체계의 구성요소이고, 다른 구성요소와 독립적으로 운영된다.

### 네임 스페이스(name space)
변수 이름이나 함수 이름과 같이 명칭을 사용하는 공간으로 소속을 나타낸다고 표현할 수 있다.

예를들어, 영희네 강아지도 흰둥이고, 철수네 강아지도 흰둥이라면 구분하기 위해 영희네 흰둥이, 철수네 흰둥이라고 언급 할 수 있다.
여기서 영희, 철수라고 하는 *소속*을 네임 스페이스라고 한다.

네임 스페이스라는 소속공간에 따라서 변수나 함수가 같은 이름임에도 다른 식으로 구분이 될 수 있다.

> 타입스크립트 1.5에서 명명법이 변경되었다.
> “내부 모듈(Internal modules)” 는 “네임스페이스” 가 되었다.
> “외부 모듈(External modules)” 은 “모듈(modules)” 이 되어 ES6 의 용어와 맞췄다.
> (`module X {` 는 `namespace X {` 와 동일하며 후자가 선호된다.)










