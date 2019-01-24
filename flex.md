# flex item 의 방향과 순서
## flex
CSS flex 컨테이너의 공간상에서 item 이 차지하는 공간을 알맞게 키우거나  줄이게 하는 property 이다.
Flex iteme 들은 자신의 minimum content size 보다 더 작게 줄어들지 않는다. 이걸 바꾸려면 해당 아이템의 `min-width` 이나 `min-height` 값을 변경해야한다.

`flex-grow` & `flex-shrink` & `flex-basis`

의 값을 한번에 설정하는 shorthand property 이다.

대부분의 경우, `flex` 의 값으로는 `auto`, `initial`, `none`, `<positive uitless number>` 이 사용된다.

*auto*
아이템의 크기는 해당 아이템의 width 나 height 의 크기로 만들어진다. /flex container 의 공간이 남으면 해당 공간에 대하여 자기 지분을 받는다./  flex container 의 공간이 줄어들면 아이템의 공간도 줄어든다. 
-> `flex: 1 1 auto` 와 값이 같다.
Ex) flex 공간안에 값이 `auto` 인 아이템이 3개 있으면 flex 공간의 주어진 크기안에서 3분할 해서 가져간다.

*initial*
auto 랑 똑같은데, flex contianer 가 공간이 남아도 자기 지분이 0 이어서 커지지 않는다. 하지만 줄어들 때에는 auto 랑 똑같이 줄어든다.
-> `flex: 0 1 auto` 와 값이 같다.

*none*
Flex container 안에서 자기 크기를 지키고 있다. 여유공간이 늘어난다고 커지지 않고, 줄어든다고해서 줄어들지도 않는다.
-> `flex: 0 0 auto`

*???*
`flex: 1 30px` -> ??? px 부분은 min-width 같은건가?
`flex: 1 1 100px` -> ???

## flex-direction: item의 방향을 제어
*initial* -> `flex-direction: row`
### value
* row -> ( 1  2  3 ) 가로로
* row-reverse -> ( 3  2  1 ) 가로로
* column -> ( 1  2  3 ) 세로로
* column-reverse -> ( 3  2  1 ) 세로로

## flex-wrap: 줄바꿈을 제어
*initial* -> `flex-wrap: nowrap`
### value
* nowrap -> 주어진 공간을 내용이 넘었을때 순서대로 그냥 가로로 넘어서 한줄로 나타난다.
|1	2|	3
* wrap -> 주어진 공간을 내용이 넘었을 때  그 공간에 맞게 밑으로 내려가서 순서대로 두줄로 채워진다.
|1	2|
|3	  |
* wrap-reverse -> 주어진 공간을 내용이 넘었을 때 그 공간에 맞게 아랫줄부터 채워서 두줄로 채워진다.
|3	  |
|1	2|

## flex-flow: 방향과 줄바꿈을 단축속성으로 제어
*initial* -> `flex-flow: row nowrap`

## order: 배치순서를 제어

