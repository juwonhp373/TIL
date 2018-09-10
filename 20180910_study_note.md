##  서비스용 프로젝트와 개인 프로젝트 구분
vue iniit hyunwoo/vue-template 할 때,
서비스용 프로젝트를 github page 로 만들지 않는다.
개인 프로젝트는 github page 로 만들어도 된다.
## Router 추가하는 법
Router 은 /src/router/index.js 에서 추가한다.
page 폴더에서 vue  파일,  ex) Velo.vue	를 만들고,
router/index.js 에서 
```js
import Velo from '../page/Velo';
```
로 Velo 변수에 'page/Velo.vue' 파일을 불러온다.

이후 아래 export 에서
```js
export default new Router({
	mode: 'history',
	routes: [
	{
		path: '/',       // 주소
		name: 'Hello'    // 이름
		component: Hello // Page 변수
	},
	// ... 여기에 router 를 추가한다.
	]
});
```
## 포트 번호 	변경하는 법
'config/index.js' 의 publish 에서  포트 번호를 변경하면 된다.
## SPA(Single Page web Application)
### SPA의 장점
사용자 친화적이고 빠른반응속도, 서버 요청이 적기때문에 트래픽이 적다.

### SPA의 단점
검색엔진 최적화(SEO)가 힘들며,
초기 구동시간이 오래걸림 –> 첫 페이지는 서버상 데이터를 처리해서 쏴주는 형태가 바람직하다.
## 

# 컴포넌트(Component)
- 기본 HTML 엘리먼트를 확장하여 재사용 가능한 코드를 캡슐화 하는데 도움이 된다.
- Vue 컴포넌트는 Vue 인스턴스이기도 하다. 그러므로 모든 옵션 객체를 사용할 수 있다.
- 같은 라이프사이클 훅을 사용할 수 있다.