# JavaScript 기초

## JavaScript 의 변수 선언
JavaScript에서의 변수 선언은 기본적으로 var 키워드를 사용한다.

ex)
```
var a = 10;
var b = '문자열';
var c = null;
```
## JavaScript 의 함수 선언

JavaScript의 함수는 별도의 Return type이 존재하지 않는다.

매개변수의 변수형에 대한 정의가 없이 매개변수 이름만 명시한다.

1. 기본적인 이름있는 함수를 생성하는 방법
```
function add(a,b){
	var sum = a + b;
	return sum;
}
```
2. 익명함수
```
function (a,b){

}
``` 
3. 함수도 결국에는 변수
```
var func = function(a,b){
	return a + b;
}
```
> ```
> var val = add('10', 20);
> console.log(val);
> ```
> -> '1020' 으로 나옴.
4. script 불러오는 법 

위에서부터 순서대로 실행되기 때문에  script library는 pug 위에 link처럼 적어 놓아야 한다.
```
script(src="https://code.jquery.com/jquery-3.3.1.js",  
  integrity="sha256-2Kok7MbOyxpgUVvAk/HJ2jigOSYS2auK4Pfzbm7uH60=",  
  crossorigin="anonymous")
```
실제 가져올 script 파일은 사용할 pug의 맨 밑에 적어 놓는다. (위에서 아래로 불러오기 때문)
ex)
```
script(src='/javascripts/addMessage.js')
```
5. jquery 선택자 & jquery 객체
- jquery 선택자
```
$(이 안에 id, tag, attribute, class 등이 올 수 있다.)
```
- jquery 객체
```
var $message = $('#message');
console.log($message);
```
여기서 `var $message` 는 jquery 선택자로부터 만들어진 객체이다.

6. set / get
- set
함수 안의 인자가 명시된 경우
```
$message.text('안녕 조교님!');
```
- get
함수 안의 인자가 없는 경우, 그 위치에 있는 해당 내용을 가져옴
```
var content = $message.text();
alert(content);
```
-> 이수정의 상상은 현실이 된다

7. append

선택된 대상의 자식으로 매개변수를 붙인다.
```
$message.append('<h1>WT???</h1>')
```
