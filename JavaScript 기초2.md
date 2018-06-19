# JavaScript 기초2

## kakaoProfile - test.js 수업

아래의 `#message` 은 kakaoProfile.pug 에서 상태 메세지 영역을 가리킨다.
```
var $message = $('#message');  
console.log(///);
```
> ///영역에 `$message`가 들어가면, 
> ```
> div#message.current-message-grid.flex.align-center
> ```
> '#message'가 차지하고 있는 자리 전체를 가져온다.

> ///영역에 `$message.text()` 가 들어가면,
> ```
>  이수정의 상상은 현실이 된다
> ```
> `#message`의 text를 가져온다.

> ///영역에 `$message.text('안녕 조교님!')` 가 들어가면,
> console말고 실제 화면자체에 `안녕 조교님!` 이라고 나오게 된다.
## kakaoChatRoom - addMessage.js 수업
```
var $messageField = $('.chatting-zone');  
var $send = $('#messageSend');  
var $input = $('input');
```
> `.chatting-zone` 클래스에 append로 내가 입력하는 채팅을 추가할 것이다.
> `#messageSend` id 는 일단 스마일 버튼에 달아놨고, 이 버튼을 누르면 append 될 것이다.
> `input` tag를 가져와서 jquery객체로 만든다.

```
function addMessage(){  
    console.log('called!!');  
  var text = $input.val();  
  $messageField.append(  
        `<div class="message-field flex flex-1" type="reverse">  
 <div class="profile-photo-cell" who="user"> <div class="photo"></div> </div> <div class="name-massage-grid"> <div class="name-cell flex-1" who="user">ㄱ이수정</div>  
 <div class="flex flex-1"> <div class="message-cell">${text}</div>  
 <div class="time-cell flex-1" who="user">오후 12:28</div> </div> </div> </div>`);  
  
  $input.val('');  
  
}

$send.on('click', addMessage);
```
> 함수 addMessage 에서 `console.log('called!!'); ` 는 매번 이 함수가 호출 될 때 마다 console에서 몇번 호출 되었는지 알려주는 메세지다.

> `var text = $input.val();` 는 앞서 생성한  input jquery 객체의 `.val` 부분을 ()로 set함으로 위치를 가져와서 text라는 변수에 지정해 준 것이다.

> text 변수는 `$messageField.append`의 `<html>` 안에서 message가 보여지는 `message-cell`의 위치에서 `${text}`로 사용자의 입력에 따라 message가 바뀔 수 있도록 사용 되었다.

> `$input.val('');`은 사용자가 입력하고 message가 버튼으로 올라간 뒤에 input을 비워주는 것이다.

>  `$send.on('click', addMessage);` 은 `'click'` 하면 `addMessage`가 실행 된다는 것이다.
>>`$send.on(arg1, arg2);`
>> - arg1 :  event name
>> - arg2 : 실행할 함수

