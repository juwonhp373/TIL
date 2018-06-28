# html&CSS 기초2
## word-break & word-wrap
두 속성은 줄 바꿈 위해 사용된다.
### word-break
단어의 분리를 어떻게 할 것인지 결정한다.

ex)  (공백/띄어쓰기) 날씨가 · 좋아요
ex) (음절) 날 · 씨 · 가 · 좋 · 아 · 요 ·

**속성값**
- normal(기본값)
```sass
한·글·좋·아·요,  这·是·一·些·汉·字,·and·some·Latin,·و·کمی·نوشتنن·عربی·และ·ตัวอย่าง·การเขียน·ภาษาไทย.
```
CJK(Chinese, Japanese, Korean) -> 중단점: 공백(띄어쓰기, 하이픈'-')
non-CJK -> 중단점: 음절
- break-all
```sass
한·글·어·좋·아·요,  这·是·一·些·汉·字,·a·n·d·s·o·m·e·L·a·t·i·n,·و·ﮐ·ﻤ·ﻰ·ﻧ·ﻮ·ﺷ·ﺘ·ﻦ·ﻋ·ﺮ·ﺑ·ﻰ,·แ·ล·ะ·ตั·ว·อ·ย่·า·ง·ก·า·ร·เ·ขี·ย·น·ภ·า·ษ·า·ไ·ท·ย.
```
CJK, non-CJK -> 중단점: 음절
- keep-all
```sass
한글·좋아요,这是一些汉字,·and·some·Latin,·و·کمی·نوشتنن·عربی,·และตัวอย่างการเขียนภาษาไทย.
```
CJK -> 중단점: 공백(띄어쓰기, 하이픈'-', 그 외 기호)
non-CJK -> 중단점: 공백(띄어쓰기, 하이픈'-')


### word-wrap
박스의 가로 영역을 넘친 단어 내에서 임의의 분리 여부를 결정한다.

이때, 넘친 단어의 임의의 분리는 **음절**에서 발생하며 **`white-space`** 속성이 기본값(`normal`)일 때만 적용된다.

ex)  
[![](http://wit.nts-corp.com/wp-content/uploads/2017/06/-46)](http://wit.nts-corp.com/wp-content/uploads/2017/06/-46)

**속성값**
- normal(기본값)
[속성값에 따라 박스 가로 영역을 단어가 넘치는지 유무]
CJK -> 단어넘침 X
non-CJK -> 단어넘침 O

- break-word
[속성값에 따라 박스 가로 영역을 단어가 넘치는지 유무]
CJK -> 단어넘침 X
non-CJK -> 단어넘침 X

## white-space 
속성은 어떤 요소(element)안의 공백(whitespace)이 어떻게 처리될지를 나타내는데 사용된다.
**속성값**
[![](https://image.ibb.co/cwte0T/image.png)](https://developer.mozilla.org/ko/docs/Web/CSS/white-space)

- Keyword values
	- normal(기본값)
	: 연속된 공백이 하나로 병합된다. 글이 길어지면 텍스트가 자동 줄바꿈 된다.(wrap)
![](https://image.ibb.co/iYyZZo/image.png)
	- nowrap
	: 연속된 공백이 하나로 병합된다. 글이 길어져도 줄바꿈 되지 않고 같은줄에 계속 표시 한다.
![](https://image.ibb.co/fJOZZo/image.png)
	- pre
	: 공백을 코드에 있는 그대로 표시한다. `<pre>`태그처럼 행동한다. 코드에 줄바꿈이 없다면 줄바꿈이 되지 않는다.
![](https://image.ibb.co/cKc078/image.png)
	- pre-wrap
	: 공백을 코드에 있는 그대로 표시한다. 코드에 줄바꿈이 없어도 자동 줄바꿈이 된다.
![](https://image.ibb.co/cvYF78/image.png)
	- pre-line
	: 연속된 공백이 하나로 병합된다. 코드에 줄바꿈이 없어도 자동 줄바꿈이 되며, 코드에 줄바꿈이 있을 때도 그대로 표시한다.
![](https://image.ibb.co/dR0dS8/image.png)

- Global values
	- inherit
	- initial
	- unset 
## 갑자기 html!

- html 코드 작성시 공백은 최대 1개만 표신된다.
하나 이상의 공백을 표시하기 위해선 `&nbsp;`(non breaking space) 를 써야 한다.
하지만 **`<pre>` 태그**를 사용하면 공백이나 줄바꿈을 있는 그대로 표시한다.

- **`<br>`태그**는 line break의 약자로, 줄바꿈 할 때 사용한다. `<br>`태그는  끝태그가 없는 빈 태그(empty tag)이다.  
