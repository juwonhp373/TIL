# Navigation drawer

`v-toolbar` 에다가 `v-for` 넣으면 toolbar 처럼 색 다른한줄이 여러개 생성된다.
`v-list` 에다가 `v-for` 넣으면 같은 한 줄에 들어감.
`v-list-tile` 에 넣으면 toolbar 와 상관없이 한줄씩 여러개가 생성된다.

`v-for` 사용했을 때 `{{ item.tool }}` 이렇게 받았다.
items 배열안에 3개의 아이템이 있고 그중 하나는 tool 이 없을 때, 없는것도 자리는 생성된다. 아무것도 없고 비어있는 한줄.

## <template>

`v-navigation-drawer` -> navigation drawer 자체
`v-toolbar` -> navigation drawer 내의 기능들의 주제
`v-list` -> ?
`v-list-tile`
`v-list-tile-title class="title"`
-> class=“title” 은 왜 붙인것???

`v-divider` -> 말그대로 디바이더

`v-list dense class="pt-0"`
_ `dense` -> ?
_ `class=“pt-0”` -> 왜 붙였을까 이것도
`v-list-tile v-for=“item in items” :key=“item.title” @click=“”`
_ `v-for="item in items"` -> script에 있는 items 를 여기서는 item 으로 받아서 사용할 것이다.
_ `:key="item.title"` -> \* `@click=“”` ->
-> items 배열 안에 5개가 있으면 이 `v-list-tile` 안의 것들이 5번 반복.
-> 여기까지만 써도 아무것도 쓰여있지 않은 버튼처럼 눌리는 타일들이 생성됨.

`v-list-tile-action` -> ? 이건 뭘깡
`v-icon {{ item.icon }}` -> 상위에서 item 의 배열이 반복될 때마다 배열에 있는 icon 을 넣어준다.

`v-list-tile-content` -> ?
`v-list-tile-title {{ item.title }}` -> 마찬가지로 상위에서 item 의 뱌열이 반복될 때마다 배열에 있는 title 을 넣어준다.

## <script>

```javascript
export default {
  data() {
    return {
      items: [
        { title: 'Home', icon: 'home' },
        { title: 'About', icon: 'settings' },
      ],
    };
  },
};
```

# Various Navigation-drawer

## Colored drawer

## Permanent floating drawer

## Avatars

## Temporary

## Dark theme

## Combined drawers

## Nested lists

## Mini

`vini-variant.sync` prop 을 사용하여 제어하는 미니-변형 이 있다.

처음에 `v-navigation-drawer` 에서 아래와 같이 한다.
`v-navigation-drawer v-model=“drawer” :mini-variant.sync="mini" hide-overlay stateless`

닫는 버튼을 위해
`v-list-tile-action`
`v-btn icon @click.stop="mini = !mini"`
`v-icon`

# 단어정리

- pre-configured: 미리 구성된.
- right out of the box: 개봉 후 즉시사용.

# References

[Vuetify_Navigation-drawers](https://vuetifyjs.com/ko/components/navigation-drawers)
