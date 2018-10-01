# Vuex 기초 1.
> 2018.10.01 수업내용.
***
프로젝트의 'vuex' 폴더에 'store.js' 파일을 만든다.

'page' 폴더에 'Hello.vue' 과 'Vue.test.vue' 두 파일을 사용해서 예제를 만들어 볼 것이다.

## Vuex 사용이유
각 컴포넌트는 자기자신만의 상태(data 옵션)를 가질 수 있다.

![로컬 컴포넌트 상태만을 이용](https://steemitimages.com/DQmezqWmYzfvM9eCvoiowzbySHedELg4oEYD8Px6HBwoMEi/vuex01.jpg)
> 로컬 컴포넌트 상태만을 이용했을 때의 구조다.

하지만 이 구조대로라면 각 컴포넌트들이 관리하고 있는 상태를 props 로 전달하는 것에는 한계가 있을거고, 상태를 변경하기 위해 event 를 emit(방출) 하는 것은 복잡할 것이다.

따라서 구조를 바꿔서,
모든 상태정보를 최상위 부모 컴포넌트에 저장하고 자식 컴포넌트로 props 를 이용해 전달하여 화면에 나타낸다.

상태정보를 변경할 때는 이벤트버스 객체를 이용해 Event를 발생시켜 최상위 부모 컴포넌트로 변경하고자 하는 정보를 전달하는 것이다.

![](https://steemitimages.com/0x0/https://github.com/stepanowon/vuejs_book/blob/master/vuex/vuex_images/vuex02.jpg?raw=true)

하지만 이 방법도 문제점이 있다_???
