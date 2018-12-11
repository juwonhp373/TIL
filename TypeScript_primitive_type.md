# TypeScript 기본 Type
### Boolean
true/false 값을 가지는 `boolean`

```typescript
let isDone: boolean = false;
```

### Number
모든 숫자는 부동 소수점 값이고 `number` 타입을 가진다.
16진수 및 10진수 리터럴 ( 소스 코드의 고정된 값 )외에도 바이너리( 2진수 ) 및 8진수를 지원한다.

```typescript
let decimal: number = 6;
let hex: number = 0xf00d;
let binary: number = 0b1010;
let octal: number = 0o744;
```

### String
문자열 데이터를 표현하기 위해 큰 따옴표(“) 혹은 작은 따옴표(‘)를 사용한다.

```typescript
let color: string = "blue";
color = 'red';
```

문자열이 여러 행에 걸쳐있고 표현식을 포함 할 수 있는 /template string/을 사용할 수 도 있다.
이러한 문자열은 백틱/백 쿼트( .md 파일에 코드 쓸 때 쓰는 문자 ) 문자로 둘러싸여 있었고, `${expr}`를 이용하여 표현식을 포함 할 수 있다.

```typescript
let fullName: string = `Bob Bobbington`;
let age: number = 37;
let sentence: string = `Hello, my name is ${fullName}.

I'll be ${ age + 1 } years old next month.`;
```

위 코드는 String 변수를 아래와 같이 선언하는 것과 같다.

```typescript
let sentence: string = "Hello, my name is" + fullName + ".\n\n" + "I'll be " + (age + 1) + " years old next month."; 
```

### Array
배열 타입은 두가지 방법중 하나로 작성 할 수 있다.
첫번째로, 각 타입에 `[]` 를 붙여 해당 타입의 배열을 나타낸다.

```typescript
let list: number[] = [1, 2, 3];
```

두번째로는, 일반적인 배열 타입 Array 를 사용한다.

```typescript
let list: Array<number> = [1, 2, 3];
```

### Tuple
고정된 수의 요소 타입은 알고있지만, 값의 종류가 다른 배열을 표현할 수 있다. 
예를 들어, 문자열과 숫자의 쌍을 아래와 같이 표현할 수 있다.

```typescript
//Declare a tuple type
let x: [string, number];
//Initialize it
x = ["hello", 10]; // OK
//Initialize it incorrectly
x = [10, "hello"]; // Error
```

변수 선언에 포함된 인덱스 요소의 타입은 인덱스를 이용하여 정확한 타입으로 액세스가 가능하다.
하지만, 타입이 서로 다를수가 있기 때문에 액세스한 데이터의 처리는 달라질 수 있다.

```typescript
console.log(x[0].substr(1)); // OK
console.log(x[1].substr(1)); // Error, 'number' does not have 'substr'
```
> //OK 된 console.log 는 “ello” 가 나온다.

변수 선언에 포함되지 않는 요소에 대한 액세스는 Tuple 선언에 사용된 타입의 `Union` 타입으로 사용된다.

```typescript
x[3] = "world"; // OK, 'string' can be assigned to 'string | number'

console.log(x[5].toString()); // OK, 'string' and 'number' both have 'toString'

x[6] = true; // Error, 'boolean' isn't 'string | number'
```

*substr()* 
> 문자열에서 특정 부분만 골라낼 때 사용하는 메서드이다.

```javascript
string.substr( start, length )
```
> start 로 시작위치를 정하고 length로 잘라낼 문자열의 길이를 정한다.

```javascript
var str = '123456789';
document.write( '<p>substring( 1, 5 ) : ' + str.substr( 1, 5 ) + '</p>');
```

=> 23456 을 출력한다.
> 배열 1번에서 부터 5개

Start 값은 필수고, length를 지정하지 않으면 문자열의 끝까지를 가져온다.

*toString()*
> 수를 문자열로 리턴한다.

```javascript
number.toString(radix)
```

> 인자(parameters)
* 인자명: radix
* 데이터형: number
* 필수: O
* 설명: 0~36 사이의 정수
	* 2: 2진수
	* 8: 8진수
	* 16: 16진수

> 반환값(return)
String, 인자에 해당하는 진수를 리턴한다.

```javascript
var num = new Number(10);
console.log(num.toString()); // string, '10'
console.log(num.toString(2)); // string, '1010', 2진수
console.log(num.toString(8)); // string, '12', 8진수
console.log(num.toString(16)); // string, 'a', 16진수
``` 

### Enum

유용한 기능중 하나이다. 숫자값 데이터 셋에 사람이 더 친숙한 이름을 지정하는 방법이다.

```typescript
enum Color {Red, Green, Blue}
let c: Color = Color.Green;
```

기본적으로 enum은 0부터 시작하여 멤버의 번호 매기기를 시작한다. 멤버 중 하나의 값을 수동으로 설정하여 변경할 수 있다.
예를 들어, 이전 예제를 0 대신 1 로 시작할 수 있다.

```typescript
enum Color {Red = 1, Green, Blue}
let c: Color = Color.Green;
```

OR

```typescript
enum Color {Red = 1, Green = 2, Blue = 4}
let c: Color = Color.Green;
```

enum 의 편리한 기능은 숫자 값에서 enum 의 값 이름으로 이동할 수 있다는 것이다.
예를 들어 , 값이 2 이지만 위의 색상 enum 에 매핑된 것이 확실하지 않은 경우 해당 이름을 찾을 수 있습니다.

```typescript
enum Color {Red = 1, Green, Blue}
let colorName: string = color[2];

alert(colorName);
```

> 어떻게 나와????????????????????????????????????

### Any
값을 자신 또는 타사 라이브러리의 동적 콘테츠에서 가져오는 것과 같이 프로그램을 작성할 때 알지 못하는 변수 유형을 설명해야 할 수도 있다.
이경우 컴파일시 타입 검사를 하지 않고 지나도록 해야한다.
이런 방법을 위해 `any` 타입을 사용한다.

```typescript
let notSure: any = 4;
notSure = "maybe a string instead";
notSure = false; // OK, definitely boolean
```

기존 JavaScript와 같이 작업하는 강력한 방법중 하나이다.
컴파일하는 동안 타입 검사를 옵트 인(opt-in) 하거나 옵트 아웃(opt-out) 할 수 있다.

JavaScript 의 `object` 타입이 비슷한 역할을 한다.
하지만, `object` 타입의 변수는 값을 할당할 수만 있다.
실제 존재하는 메소드라도 임의의 메소드를 호출 할 수는 없다.

```typescript
let notSure: any = 4;
notSure.ifItExists(); // OK, ifItExists might exist at runtime
notSure.toFixed(); // OK, toFixed exists (but the compiler doesn't check)

let prettySure: Object = 4;
prettySure.toFixed(); // Error: Property 'toFixed' doesn't exist on type 'Object'
```

> ??????????????????? 이게모양

`any` 타입은 타입의 일부분을 알고 있다면 편리하지만 그렇지 않을 수도 있다.
예를 들어, 배열이 있고, 배열에 있는 값은 다른 타입이 혼합되어 있을 수도 있다.

```typescript
let list: any[] = [1, true, "free"];

list[1] = 100;
```

> ????????????????????????

### Void
타입이 전혀 없다는 것에서 `any` 의 반대 의미와 비슷하다.
일반적으로 값을 반환하지 않는 함수의 반환 유형으로 사용한다.

```typescript
function warnUser(): void {
	alert("This is my warning message");
}
```

`void` 타입의 변수 선언은 `undefined` 또는 `null` 만 할당할 수 있기 때문에 그다지 유용하지 않다.

```typescript
let unusable: void = undefined;
```

### Null 과 Undefined
`undefined` 와 `null` 은 실제로 각각 `undefined` 와 `null` 이라는 이름의 타입을 가지고 있다.
`void` 와 매우 비슷하게, 그 자체로 매우 유용하지는 않다.

```typescript
// Not much else we can assign to these variables!
let u: undefined = undefined;
let n: null = null;
```

기본적으로 `null` 과  `undefined` 는 다른 모든 유형의 하위 유형이다.
즉, `null` 과 `undefined` 를 `number` 와 같은 것에 할당할 수 있다.

`--strictNullChecks` 플래그를 사용할 경우 `null` 과  `undefined` 는 `void` 와 각각의 타입 변수에만 할당 가능하다.
이렇게 하면 많은 일반적인 오류를 피할 수 있다.
`string` 또는 `null` 또는 `undefined` 를 전달하고자 하는 경우, union 타입 `string | null | undefined` 을 사용할 수 있다.

** 가능하면 `--strictNullChecks` 의 사용을 권장한다. **
** 목적상 우리는 플래그가 꺼져있다고 가정한다. ** ????????????????????????

### Never
절대로 발생하지 않는 값의 타입을 나타낸다.
예를 들어,
	* 함수표현식의 리턴 타입이거나, 
	* 항상 예외를 던지는 화살표 함수 표현식이거나, 
	* 리턴하지 않는 표현식이다.
변수는 결코 true 가 될 수 없는 어떤 타입의 가드에 의해 좁혀질 때, 타입 `never` 을 획득한다.

모든 타입의 서브 타입이며, 모든 타입에 assign 가능하다.
하지만 어떤 타입도 `never` (`never` 자체 제외) 의 하위 타입이 아니고 assign 할 수 없다.

`never` 을 반환하는 함수의 몇 가지 예는 다음과 같다.

```typescript
// Function returning never must have unreachable end point
function error(message: string): never {
	throw new Error(message);
}

// Inferred return type is never
function fail() {
	return error("Something failed");
}

// Function returning never must have unreachable end point
function infiniteLoop(): never {
	while (true) {
	}
}
```

> ???????????????????????????

### Type assertions
어떤 값에 대해 프로그래머는 때때로 TypeScript 보다 더 많은 정보를 알 수 있다.
이런 경우는 어떤 엔티티(entity = 개체)의 타입이 현재 타입보다 더 구체적인 타입을 알고 있을 때이다.

컴파일러에게 “나를 믿어, 내가 하고있는 일을 잘 알아” 라고 말하는 방법이다.
다른 언어의 타입 변환과 비슷하지만 특별한 검사나 데이터 재구성을 수행 하지는 않는다.
런타임에 영향을 미치지 않으며, 컴파일러에서만 사용된다.
TypeScript는 프로그래머가 필요한 특수 검사를 수행했다고 가정한다.

두가지 형식이 있다.
* *angle-bracket(<>)*

```typescript
let someValue: any = "this is a string";

let strLength: number = (<string>someValue).length;
```

* *as*

```typescript
let someValue: any = "this is a string";

let strLength: number = (someValue as string).length;
```

두가지 방법은 동일한 역할을 하기 때문에 어떤것을 사용할지는 선택의 문제이다.
그러나 TypeScript 를 JSX 와 함께 사용할 경우에는 `as` 스타일의 assertion 만 허용된다.

### `let` 에 대해
기존에 알고있는 JavaScript 의 `var` 키워드 대신 `let` 	키워드를 사용했다.
`let` 키워드는 실제로 TypeScript 에서 사용할 수 있는 새로운 JavaScript 구문이다.
JavaScript 의 일반적 문제는 `let` 을 사용하여 완화되므로 가능할 때마다 `var` 대신 사용하면 좋다.



