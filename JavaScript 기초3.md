# JavaScript 기초3

## calculator - calculator.js 수업
calculator을 만들기 위한 생각의 흐름을 정리하자면,
1. 숫자 버튼을 누를때 그 특정 버튼의 숫자들이 화면에 출력 되어야 한다.
2. 그 숫자들을 모아서 눌릴 때 마다 저장하는 변수가 필요하다.
3. 모두 모아서 저장된 변수가 화면에 출력 될 수 있게 출력될 부분을 가져와야한다.
```
var $numbers = $('.button.number');  
var $result = $('.show-result-field');  
var value = 0;
```
> 여기서 `console.log($numbers);` 하면 전체 number이 들어옴.

<br>

```
$numbers.on('click', function () {
	console.log(this);
	var num = &(this).text();
	if (value === 0) {
		value = num
	} else {
		value += num
	}
	$result.text(value);
});
```
>  `var num = &(this).text();` 누르는 버튼의 text인 숫자를 가져온다.

>  if, else 문을 사용하여 기본적으로 0으로 설정되어 있는 화면이 깔끔하게 나오도록 했다. 

<br>

```
$('util[command]').on('click', function () {
	value = value + '';
	if(!isNaN(value[value.length -1])) {
	value += $(this).attr('command');
	$result.text(value);
	}
});
```
> `value = value + '';` value를 ' ' 를 더해 줌으로 문자열으로 만들어 준다.

> 문자열로 만들었으니, 마지막 문자에 배열로 접근이 가능하다.

> 우리가 알고싶은 것은 마지막 문자가 숫자인지 아닌지를 알고 숫자라면 버튼이 한번씩 눌릴 수 있게 만드는 것이다.

> 마지막 문자의 접근은 `value[value.length-1]` 을 통해 접근이 가능하다.

>  이제 숫자인지 아닌지를 알아내야 하는데, 이것은 `isNaN();` 함수를 이용해 알아 낼 수 있다. 

> ### isNaN(); 
> NaN은 Not a Number의 약자로, `isNaN(10);` 이라면, 숫자이기 때문에 `false` 가 반환 된다.
> ex)
> `isNaN('10')` -> `false`
> `isNaN('+')` -> `true`

> ### attribute을 JavaScript에서  쓰는 법
> ```
> .button.other(command='ac')
> ```
> pug에서 이렇게 쓰였다면,
> ```
> var $ac = $('.button.other[command=ac]');  
>//console.log($apple);
> ```
> 이렇게 js에 가져온다.

<br>

- id로 가져왔을 때,
```
$('#ac').on('click', function () {  
    value = 0;  
  $result.text(value);  
});  
  
$('#plusminus').on('click', function () {  
    value = -eval(value);  
  $result.text(value);  
});  
  
$('#percentage').on('click', function () {  
    value = eval(value) * 0.01;  
  $result.text(value);  
});
```
> id를 가져와서 기능을 주었다.
> 
> `#ac`는 value값을 0으로 초기화,
> `#plusminus`는 value값에 전체 계산을 eval로 한뒤, -붙여서 부호 바꾸기,
> `#percentage`는 value값에 전체계산을 eval로 한뒤, 0.01곱하기.

<br>

- attribute로 가져왔을 때,
```
$('.other[command]').on('click', function () {  
    console.log(this)  
    var command = $(this).attr('command');  
  switch (command) {  
        case 'ac' :  
            value = 0;  
			break  
		case 'plusminus' :  
            value = -eval(value);  
			break  
		case 'percentage' :  
            value = eval(value) * 0.01;
            break
  }  
    $result.text(value);  
})
```
> other 버튼들을 switch문으로 묶어보았다.

> switch문을 쓸 때,  `switch ($(this).attr('command'))` 라고 쓰기 보다 위 처럼 `var command` 객체를 만들어서 알아보기 쉽게 한다.

<br>

```
$('#equal').on('click', function () {  
    console.log(this);  
  value = eval(value);  
  $result.text(value);
```
> `#equal`은 다른 +,-,/,* 와 다르게 따로 뽑아서 기능을 준다.
> value를 eval로 계산 해주면 된다.
