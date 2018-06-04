git push 하는 법

검색으로 git bash를 찾아 들어간다.

ls 으로 내 파일들 다 확인가능

cd Develop에 들어가

ls

안에 Java폴더만 있어서 Web 폴더도 만들어 줌 -> mkdir Web 로

Chrome 으로 내 github.com 접속

Repositories에서 TIL의 HTTPS주소 복사

다시 gitbash 돌아가서
git clone https://github.com/juwonhp373/TIL.git 입력(gitbash에서 붙여넣기는 shift+Fn+insert/ 복사하기는 ctrl+Fn+insert)

이렇게 하면, chrome의 repository를 clone해서 내 폴더인 Develop에 가져온거임

내가 올릴 파일을 Markdown에서 바로 menu에서 Export to disk로 파일 을 TIL 폴더에 저장시키거나 Sublime Text에서 .md 파일로 TIL에 저장한다.
-> HowToGitPush.md

gitbash가서 cd TIL로 TIL 폴더로 들어가서 git status 쳐서 올라간 파일 과 안올라간 파일을 볼 수 있다. 빨간거는 안올린거.
