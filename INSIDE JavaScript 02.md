# INSIDE JavaScript 02
## Chapter 03
### 참조 타입
자바스크립트에서 기본타입을 제외한 모든 값은 객체다.
- 자바스크립트에서 객체는 단순히 '이름(key):값(value)' 형태의 프로퍼티들을 저장하는 컨테이너다.
- 기본타입은 하나의 값만을 가지는데 비해, 참조타입인 객체는 여러개의 프로퍼티들을 포함 할 수 있다.
- 이러한 객체의 프로퍼티는 기본 타입의 값을 포함하거나 다른 객체를 가리킬 수도 있다.
- 객체의 프로퍼티는 함수로 포함 할 수 있으며 이러한 프로퍼티를 **메서드**라 부른다.
*배열(Array)*
*함수(Function)*
*정규표현식*

### 객체 생성
객제를 생성하는 방법은 크게 세가지있다.
- Object() 객체 생성자 함수 이용
```js
// 빈 객체 생성 
var foo = new Object();

// foo 객체 프로퍼티 생성
foo.name = 'foo';
foo.age = '30';
foo.gender = 'male';

console.log(typeof foo); // object
console.log(foo); // { name: 'foo', age: 30, gender: 'male'}
```
- 객체 리터럴(표기법) 이용
	-	객체를 생성하는 표기법을 의미한다.
	-	객체 리터럴은 중괄호({ })를 이용해서 객체를 생성한다.
	-	{ } 안에 아무것도 적지 않은 경우는 빈 객체가 생성된다.
	-	중괄호 안에 "프로퍼티 이름":"프로퍼티 값" 형태로 표기하면, 해당 프로퍼티가 추가된 객체를 생성 할 수 있다.
	-	프로퍼티 이름은 문자열이나 숫자가 올 수 있다.
	-	프로퍼티 값으로는 자바스크립트의 값을 나타내는 어떤 표현식도 올 수 있으며, 이 값이 함수일 경우 **메서드** 라고 부른다.

```js
var foo = {
	name: 'foo',
	age: 30,
	gender: 'male'
}:
```
- 생성자 함수 이용
	- 함수를 통해서도 객체를 생성 할 수 있다.
	- 4장에서 자세히!!! 

### 객체 프로퍼티 읽기/쓰기/ 갱신
객체는 새로운 값을 가진 프로퍼티를 생성하고, 생성된 프로퍼티에 접근해서 해당 값을 읽거나 또는 원하는 값으로 프로퍼티의 값을 갱신할 수 있다.

객체의 프로퍼티에 접근하는 방법엔 두가지 방법이 있다. 
- 대괄호([ ]) 표기법
- 마침표( . ) 표기법
```js
// 객체 리터럴 방식을 통한 foo 객체 생성
var = foo = {
	name: 'foo',
	major: 'computer science'
};

//객체 프로퍼티 읽기
console.log(foo.name); // foo
console.log(foo['name']); // foo

//객체 프로퍼티 갱신
foo.major = 'electronics engineering';
console.log(foo.major); // electronics engineering

//객체 프로퍼티 동적 생성
foo.age = 30;
console.log(foo.age); // 30

//대괄호 표기법만을 사용해야하는 경우
//: 접근하려는 프로퍼티가 표현식이거나 예약어일 경우.
//full-name -> '-'연산자가 있는 표현식
foo['full-name'] = 'foo bar';
console.log(foo['full-name']); // foo bar
console.log(foo.full-name); // NaN
//foo.full - name
//undefined - undefined 의 연산 결과는 NaN.

```
> NaN(Not a Number)
> : 수치연산을 해서 정상적인 값을 얻지 못할 때 출력되는 값이다. 
