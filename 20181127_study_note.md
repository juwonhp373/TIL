# Vue CLI 3 을 이용한 vue 어플리케이션 생성방법


1. 원하는 폴더에 새로운 프로젝트를 만든다
ex) cd Develop 안에

2. npm install -g @vue/cli => vue 최신버전 다운받기
				-g => global 전체에 다운받는것

			-g	=> cd /usr/local/bin/ 위치에 실행파일들이 다운됨.


	vue/cli 템플릿을 생성하는 애 프로젝트를 만들기 위한 애 생성을 해주는 애 
	package.js 를 만들어서 각 프로젝트가 생성될 떄 넣어줌

	vue/router 프로젝트 안에서 필요한것



예를 들어 폴더를 열어서 안에 `npm install lodash` 하면 "node_modules" 안에 lodash 가 깔린다.
`npm install lodash --save` 를 하면 "package.json" 안에 dependencies 에 lodash 가 기록이 된다. 외부로 프로젝트를 보냈을 때 node_module 은 보내지 않고 package.js 만 보낸다(설계도) 그러면 사람들이 내 프로젝트를 받았을 때 `npm install` 을 하면 dependencies 를 보고 거기에 있는 것들을 컴퓨터가 깐다.

npm(node package manager)

node_module 은 OS 의존적이다. 그래서 안올린다. window 에 있는 node_module 을 mac 에서 돌렸을 때 안되는 경우가 많다. 반대도 마찬가지.



3. `npm install @vue/cli-init -g`
이전 버전들도 사용할 수 있도록 해주는 것.

4. `vue create vue3test` 원하는 위치에 원하는 프로젝트를 만들어준다.

_

[Vue CLI v3.1.3]

? Please pick a present: Manually select features

? Check the features needed for your project: Babel, Router, Vuex, CSS Pre-processors, Linter

? Use history mode for router? Yes

? Pick a CSS pre-processor (PostCSS, Autoprefixer and CSS Modules are supported by default): Sass/SCSS

? Pick a linter / formatter config: Prettier

? Pick additional lint features: Lint on save, Lint and fix on commit

? Where do you prefer placing config for Babel, PostCSS, ESLint, etc.?
In package.json

? Save this as a preset for future projects? No
_


`vue create vue3test` 는 `npm install @vue/cli -g` 를 해서 쓸 수 있는 것.
전 버전에는 `vue init hyunwoo/vue-template vue3 test` 을 했었음. 그래서 새로운 프로젝트 생성할 때 `vue create vue3test` 를 쓰려면 새 버전을 받고서 써야함.



* `rm -rf vue3test` => "vue3test" 프로젝트 삭제.


5. `vue add vuetify`

_

? Choose a preset: Default (recommended)
_

6. `vue init posva/vue-plugin-template juwon-first-plugin`

_

? Plugin name			juwon-first-plugin

? Library name			JuwonFirstPlugin

? Plugin description	A Vue.js Plugin

? Current version		0.0.0

? Author				Juwon Hong <juwonhp373@gmail.com>

? GitHub Account		juwonhp373@gmail.com

? Bundler				rollup
_


7. `npm install`

8. `npm adduser`

=> npm 회원가입

_

Username: juwonhp373

password: **************

Email: (this IS public) juwonhp373@gmail.com

Logged in as juwonhp373 on https://registry.npmjs.org/.

Juwonui-MacBook-Pro: juwon-first-plugin penguin$ npm publish --access public
_










