# GitHub 프로젝트 생성
## GitHub
1. Repositories -> new
2. Repository name 입력 -> Create repository
3. *…or push an existing repository from the command line* 에 있는 두줄 복사

## Terminal
1. 파일 넣고싶은 폴더 안에서 `vue create {{repository name}}`
	* 버젼 업그레이드가 있으면 `npm install @vue/cli -g`
2. *Vue CLI v3.8.4*
? *Please pick a preset:* Manually select features
? *Check the features needed for your project:* Babel, TS, PWA, Router, Vuex, CSS Pre-processors, Linter
? *Use class-style component syntax?* Yes
? *Use Babel alongside TypeScript (required for modern mode, auto-detected polyfills, transpiling JSX)?* Yes
? *Use history mode for router? (Requires proper server setup for index fallback in production)* Yes
? *Pick a CSS pre-processor (PostCSS, Autoprefixer and CSS Modules are supported by default):* Sass/SCSS (with dart-sass)
? *Pick a linter / formatter config:* TSLint
? *Pick additional lint features:* Lint on save, Lint and fix on commit
? *Where do you prefer placing config for Babel, PostCSS, ESLint, etc.?* In package.json
? *Save this as a preset for future projects?* No

3. 설정 완료 후 `cd ..` 인가로 내가 만든 {{repository name}} 파일 안에 GitHub 에서 복사해온 내용 붙여넣기
4. `code .` 하면 visual studio code 에서 프로젝트 열림




