# typescript 설치

```
npm install -g typescript
```

(예시) greeter.ts 확장자의 파일을 만들어서 코딩을 한 다음에,
tsc greeter.ts 를 터미널에 치면
greeter.js 로 컴파일 된다.


컴파일 할 때 문제가 있으면 error 을 만들어주며 js 파일로 컴파일 해준다. 

<br>

type annotation 이란, 아래 코드의 person 옆의 string 이다.

type과 다른걸 넣으면 에러를 보여준다.

ex) function greeter의 parameter가 string type일 때,
    대입한 값이 number[] 이기 때문에 에러가 나온다.

```typescript
function greeter(person: string) {
    return "Hello, " + person;
}

let user = [0, 1, 2];

document.body.innerHTML = greeter(user);
```


## interface

interface가 있다. 
객체가 interface와 호환된다.

```typescript
interface Person {
    firstName: string;
    lastName: string;
}

function greeter(person: Person) {
    return "Hello, " + person.firstName + " " + person.lastName;
}

let user = { firstName: "Jane", lastName: "User" };

document.body.innerHTML = greeter(user);

```

## class

class를 사용할 수 있다.
결과값은 위의 코드와 같다.

```typescript
class Student {
    fullName: string;
    constructor(public firstName: string, public middleInitial: string, public lastName: string) {
        this.fullName = firstName + " " + middleInitial + " " + lastName;
    }
}

interface Person {
    firstName: string;
    lastName: string;
}

function greeter(person : Person) {
    return "Hello, " + person.firstName + " " + person.lastName;
}

let user = new Student("Jane", "M.", "User");

document.body.innerHTML = greeter(user);
```

<br>

웹에서 실행하기 위해서 아래의 html 코드를 만든다.

```html
<!DOCTYPE html>
<html>
    <head><title>TypeScript Greeter</title></head>
    <body>
        <script src="person2.js"></script>
    </body>
</html>
```
