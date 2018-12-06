# VisualStudioCode 기반 프로젝트 생성 및 사용
1. 원하는 폴더 안에 프로젝트 파일을 생성한다.
> `cd Project.Web`
> `mkdir second-ts`

2. `npm init` => ( package.json 생성 )

3.  
	> package name: ( first-ts )
	> version: ( 1.0.0 ) 0.0.0
	> description: my first ts project
	> entry point: ( index.js )
	> test command:
	> git repository:
	> keywords: 
	> author: juwonhp373@gmail.com
	>license: ( ISC ) MIT
	
	> Is this OK? ( yes ) y

4. `code .` 

5. `dist` 폴더와
`src` 폴더를 생성한다.

6. 프로젝트 생성시 `npm install typescript`
=> ( package-lock.json 생성 )

7. `npx tsc --init`
=> ( tsconfig.json 생성 )
=> .ts 파일을 .js 로 변경

8. tsconfig.json 에서
> “sourceMap”: true,
> “outDir”: “./dist”,
주석 풀어두는게 기본 설정

9. `npx tsc` 
> .ts -> .js 바꿔주는 명령어

## 주석 설명 다는법
함수 스크롤 하고 `cmd + shft + p`
*Add Doc Comments*