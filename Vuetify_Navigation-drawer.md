# 1/15
오늘 일단 실질적으로 사용 할 수 있는 법을 외우든 익혀야한다.

- Navigation drawer 실제 사용법 익히기
- grid 익히기
- 카드 익히기

# Navigation drawer
## <template>
`v-navigation-drawer` -> navigation drawer 자체
`v-toolbar` -> navigation drawer 내의 기능들의 주제
`v-list` -> 
`v-list-tile`
`v-list-tile-title class="title"`
-> class=“title” 은 왜 붙인것???

`v-divider` -> 말그대로 디바이더

`v-list dense class="pt-0"`
	* `dense` -> ?
	* `class=“pt-0”` -> 왜 붙였을까 이것도
`v-list-tile v-for=“item in items” :key=“item.title” @click=“”`
	* `v-for="item in items"` -> script에 있는 items 를 여기서는 item 으로 받아서 사용할 것이다. 
	* `:key="item.title"` -> 
	* `@click=“”` -> 
-> items 배열 안에 5개가 있으면 이 `v-list-tile` 안의 것들이 5번 반복.
-> 여기까지만 써도 아무것도 쓰여있지 않은 버튼처럼 눌리는 타일들이 생성됨.

`v-list-tile-action` -> ? 이건 뭘깡
`v-icon {{ item.icon }}` -> 상위에서 	item 의 배열이 반복될 때마다 배열에 있는 icon 을 넣어준다.

`v-list-tile-content` -> ?
`v-list-tile-title {{ item.title }}` -> 마찬가지로 상위에서 item 의 뱌열이 반복될 때마다 배열에 있는 title 을 넣어준다.

## <script>
```javascript
export default {
  data () {
    return {
      items: [
        { title: 'Home', icon: 'home' },
        { title: 'About', icon: 'settings' }
      ]
    }
  }
}
```

# Mini
`vini-variant.sync` prop 을 사용하여 제어하는 미니-변형 이 있다.



# 단어정리
* pre-configured: 미리 구성된.
* right out of the box: 개봉 후 즉시사용.

# References
[Vuetify_Navigation-drawers](https://vuetifyjs.com/ko/components/navigation-drawers)