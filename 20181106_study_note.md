하나의 공간에 카드형식 파티클 들을 여러개 가로로 나열하고 싶을 때 보통 간단히 `display: flex`  를 주어 나타냈었다.

다른 방법으로는 하나의 공간을???????


## display
display 는 요소를 **어떻게 표시할지** 선택하는 속성이다. 

상속은 안된다.

div(block 요소)******

div 3개를 생성 했다고 했을 때, display 속성이 아무것도 적용되지 않았을 때 div 는
_한개당 가로화면 전체를 차지하고 있게된다.
_줄바꿈이 된다.

`display: inline`
_기본값으로, 요소를 inline 요소처럼 표시한다.
_따라서 앞뒤로 줄바꿈이 되지 않는다.

div 3개를 생성하고 `display: inline` 을 적용했을 때 div는
_한줄에 줄바꿈 없이 나열된다.
_div 하나당 width 와 height 가 지정되어 있어도 그게 반영되지 않는 형태로 그려진다???????


`display: block`
_요소를 block 요소처럼 표시한다.
_따라서 요소 앞뒤로 줄바꿈이 된다.

div 3개를 생성하고 `display: block` 을 적용했을 때 div는
_모두 줄바꿈이 되어 그려진다.

`display: none`
_박스가 생성되지 않는다.
_따라서 공간을 차지 하지도 않는다.

`display: inline-block`
_요소는 inline 인데 내부는 block 처럼 표시한다.
_박스 모양이 inline 처럼 옆으로 늘어선다.

div 3개를 생성하고 `display: inline-block` 을 적용했을 때 div는
_`display: inline` 과 반대로 div 하나당 width 와  height 가 지정되어 있을 때, 그 공간이 유지된다.
_한줄에 줄바꿈 없이 나열된다.
_float 속성을 적용한 것처럼 옆으로 늘어서 있다??????


## visibility
`display: none` 은 아예 공간 자체를 그리지 않는 것과 반대로
`visibility: hidden` 은 공간은 차지하지만 보이지 않는다.


## float
이 속성을 갖는 요소는 html 문서에서 **공간은 차지하되 다른 요소의 배치에 영향을 주지 않는 요소** 가 된다.

**EX**
두가지 div를 만들었을 때 두줄에 그려질 것이다.
이때, 앞의 div에 `float: left` 를 준다면
_앞의 div 가 내부 content 만큼만 공간을 차지한다.
_그 공간 바로 옆으로 뒤의 div 가 올라온게 된다.
_따라서 한줄에 두가지가 그려진다.

> `flaot: left` 
> _div 안에 있는 content 만큼만 공간을 차지하고 다른 요소에 대해 상대적으로 왼쪽으로 배치되고 무시되는 것이다.
> _다른 요소들이 flaot 속성을 지닌 태그요소의 존재를 무시하는 것이다.

원래 div 태그는 display 속성이 block 이므로 한줄을 혼자 차지하는 것이 정상이다.
하지만 앞의 div 가 float 속성을 가짐과 동시에 무시되어서 block 속성값을 가진 다음 div 가 앞의 요소를 무시한채 나란히 배치될 수 있는 것이다.


## clear
`clear: right` 속성을 가진 요소는
`float: right` 속성의 영향을 받지 않는다.

`clear: left`  를 설정하면
`float: left` 속성의 영향을 받지 않고,

`clear: both`  라고 하면
모든 float 속성의 영향을 받지 않는다. 