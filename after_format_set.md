# format 후 설정

1. 맥을 깐다( 한영처리, spotlight, )

2. brew install ( terminal )
	* 엔터 누르기
	* 비번 입력
	* `brew update`
	* `brew install node` ( node 랑 npm 이 같이 깔림)
	* `node -v`
	> v11.3.0 ( version )

3. `npm i -g npx`
	* i = install
	* -g = global

4. `npm i -g ngrok`

5.  `npm i -g http-server`

6. `cd`
	* `mkdir Develop`
	* `cd Develop`
	* `mkdir Project.Web`
	* `git clone https://github.com/hyunwoo/typescript-library-starter`
	* `cd typescript-library-starter`
	* `code .`

7. `cd`
	* `cd Develop`
	* `cd Project.Web`
	* `mkdir first-ts`
	* `cd first-ts`
	* `code .`
	
8. `npm init`
	> package name: ( first-ts )
	> version: ( 1.0.0 ) 0.0.0
	> description: my first ts project
	> entry point: (index.js)
	> test command:
	> git repository:
	> keywords: 
	> author: juwonhp373@gmail.com
	>license: ( ISC ) MIT
	
	> Is this OK? ( yes ) y

---

Mac: brew
Ubuntu: apt
CentOS: curl
RedHat: yum

npm i -g babel-cli *
npm i -g webpack *
=> Global 로 설치가 되기 때문에 버전관리에 취약하다.
=> 각 프로젝트의 환경설정을 전역이 아닌 각각 구성한다.

ngrok, http-server
=> 프로젝트 내부에 포함되는 모듈이 아니다.
=> 프로젝트 외부에서 실행하거나 독립적으로 실행하는 모듈


모든 노드프로젝트는 package.json 으로 돌아간다.
