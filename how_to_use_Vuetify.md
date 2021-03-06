# Spacing 간격

새로운 클래스를 만들지 않고 레이아웃을 업데이트한다.
margin 과 padding 을 조절하는데 유용하다.

_{속성} {방향} - {크기}_ 형식으로 적용된다.

### 속성

- m -> margin
- p -> padding

### 방향

- t -> margin-top 이나 padding-top 속성에 적용
- b -> margin-bottom 이나 padding-bottom
- l -> margin-left 이나 padding-left
- r -> margin-right 이나 padding-left

- x -> _-left 과 _-right 에 둘다 적용
- y -> _-top 과 _-bottom 에 둘다 적용
- a -> margin 이나 padding 을 모든 방향에 적용

### 크기

> margin 이나 padding…

- 0 -> 을 0 으로 설정하여 해당 속성을 제거한다.
- 1 -> 의 값을 \$spacer \* .25 로 설정.
- 2 -> \$spacer \* .5
- 3 -> \$spacer (???)
- 4 -> \$spacer \* 1.5
- 5 -> \$spacer \* 3

Ex) `px-0`
-> padding x (`*-left` 와 `*-right` 에 둘다 적용) 이기 때문에 좌우 padding 을 0 으로 설정하여 해당 속성을 제거한다.

# Display

## Display

요소의 display 속성을 지정한다. 클래스 형식은 _d-{display}_ 이다.

- d-inline-flex -> 요소의 display 속성을 inline-flex 로 정한다.
- d-flex
- d-inline-block
- d-block
- d-inline
- d-none

## Visibility

_hidden-{breakpoint}-{condition}_
현재의 뷰포트에 따라 조건부로 보여준다.

### breakpoint

> 뷰포트의 크기

- xs
- sm
- md
- lg
- xl

Device ———— Code —Types————————————————Range
Extra Small xs small to large handset < 600px
Small sm small to medium tablet 600px > < 960px
Medium md large tablet to laptop 960px > < 1264*
Large lg desktop 1264 > < 1904px*
Extra large xl 4k and ultra-wides > 1904px\*

> /\* -16 on desktop/

### condition

- only -> xs 에서 xl 까지 해당 뷰포트 크기에서만 숨긴다.
- and-down -> sm 에서 lg 까지 해당 브레이크 포인트보다 작거나 같은 요소를 숨긴다.
- and-up -> sm 에서 lg 까지 해당 브레이크 포인트보다 크거나 같은 크기에서 요소를 숨긴다.

Media types 는 `only` condition 으로  
`hidden-screen-only` 와 `hidden-print-only` 지원되고 있다.

# Grid System

Vuetify 는 12 point grid system 을 사용한다.
`flex-box` 를 사용한다.
5가지 타입의 media breakpoints.
Grid component 의 prop 들은 정의된 속성에 따라 파생되는 (css) 클래스들이다.
이를 이용해 (css) 헬퍼 클래스들을 prop 형태로 쉽게 사용할 수 있다.

## <template>

## <script>

```javascript
```

# 단어정리

- deprecated: 중요도가 떨어져 더 이상 사용되지 않고 앞으로는 사라지게 될 것

# References

[Vuetify_Navigation-drawers](https://vuetifyjs.com/ko/components/navigation-drawers)
