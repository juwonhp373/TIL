flex: 0 1 auto -> 기본값
flex: 0 0 auto -> none
flex: 1 1 auto -> auto
flex: 0 1 auto -> initial

margin-top: auto
> 별도의 min-height 잡지 않아도 브라우저 높이만큼 잡을 수 있다.

flex-flow: <‘flex-direction’> || <‘flex-wrap’>
> flex-flow: column wrap -> 두줄이 됐을때 순서대로
> flex-wrap 기본값 nowrap.


white-space: nowrap
overflow: hidden
text-overflow: ellipsis
> text 가 박스의 사이즈를 넘어갈때 ‘…’

white-space: nowrap
overflow: hidden
text-overflow: clip
> 박스 사이즈를 넘어가면 text 가 박스 크기 이후로 잘림.

hover 에서 overflow: visible 
> hover 했을때, 넘어가서 안보이던 text 가 보인다.


