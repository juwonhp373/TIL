# JavaScript 기초4
### $(선택자).동작함수();
$ 기호는 Jquery를 의미, Jquery에 접근 할 수 있게 해주는 식별자 이다.

선택자를 이용하여 원하는 HTML요소를 선택하고, 동작 함수를 정의하여 선택된 요소에 원하는 동작을 설정한다.
### $()함수
$() 함수는 선택된 HTML요소를 Jquery에서 이용할 수 있는 형태로 생성해주는 역할을 한다.

$() 함수의 인수로는 HTML 태그 이름 뿐만 아니라, CSS 선택자를 전달하여 특정 HTML요소를 선택할 수 있다.
> [CSS 선택자 정리](https://github.com/juwonhp373/TIL/blob/master/CSS%EC%84%A0%ED%83%9D%EC%9E%90.md)
### 호이스팅(Hoisting)
### 변수  범위(Variable Scope)
변수 범위는 변수가 존재하는 컨텍스트이다.

어디에서 변수에 접근 할 수 있는지, 그 컨텍스트에서 변수에 접근할 수 있는지를 명시적으로 나타낸다.

변수는 지역범위(local scope)와 전역 범위(global scope) 둘중 하나를 가진다.
#### 지역변수(함수 수준 범위)
대부분의 프로그래밍 언어와 달리, 자바 스크립트는 블럭-수준(block-level)의 범위를 가지고 있지 않다.

대신, 함수-수준(function-level)의 범위를 가진다.

함수 내에 정의 된 변수는 지역 범위를 가진며, 해당 함수와 내부 함수에서만 접근이 가능하다.
> *내부함수에서 외부함수의 변수 접근은 클로저(Closure)를 참고

***
```JavaScript
// 지역변수를 var키워드로 선언하지 않았을 경우, 그것은 전역-범위(global-scope)가 된다.

var name = "Michael Jackson"; // 전역 변수

function showCelebrityName() {

     console.log(name);
}

function showOrdinaryPersonName() {

     name = "Johnny Evers"; // 전역변수 name을 변경해 버린다.

     console.log(name);
}

showCelebrityName(); // Michael Jackson

showOrdinaryPersonName(); // Johnny Evers
//실행하는 순간 변경해 버린다.
// 이제 전역변수 name은 Johny Evers이다.

showCelebrityName(); // Johnny Evers
```
- 지역변수는 함수 내에서 전역변수보다 높은 우선순위를 가진다.
```JavaScript
var name = "Paul";

function users() {

     var name = "Jack";

     console.log(name);
}

users(); // Jack
```
#### 전역변수
모든 전역변수는 window객체와 연결된다.

window객체를 통해 모든 전역변수에 접근이 가능하다.
```JavaScript
var myName = "Amy";
console.log(window.myName); // Amy
console.log("myName" in window); // true
```
### var, let, const 차이
- `var` 는 function-scoped
- `let` , `const`는 blocked-scoped 

