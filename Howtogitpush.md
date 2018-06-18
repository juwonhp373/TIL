# How_to_GitPush

1. 검색해서 git bash 들어간다.
2. `ls` 으로 내 파일들 다 확인 가능하다.
3. `cd Develop`에 들어간다.
4. `ls`
5. 안에 Java 폴더만 있어서 Web 폴더도 만들어 준다. -> `mkdir Web`
6. Chrome 으로 내 github 접속한다.
7. Repositories 에서 TIL 의 HTTPS 주소 복사한다.
8. 다시 git bash 돌아가서
   `git clone https://github.com/juwonhp373/TIL.git ` 입력한다.
   >gitbash에서 붙여넣기는 shift+Fn+insert/ 복사하기는 ctrl+Fn+insert
  
   >이렇게 하면, chrome의 repository를 clone해서 내 폴더인 Develop에 가져온 것이다.
9. 내가 올릴 파일을 Markdown에서 바로 menu에서 Export to disk로 파일 을 TIL 폴더에 저장시키거나 Sublime Text에서 .md 파일로 TIL에 저장한다.
-> HowToGitPush.md
10. gitbash가서 `cd TIL`로 TIL 폴더로 들어가서 `git status` 쳐서 올라간 파일 과 안올라간 파일을 볼 수 있다(빨간거는 안올린거).
11. `git add HowToGitPush.md`하면 올라간다.
12. 다시 `git status`를 확인해보면 올라가있는것을 초록색으로 확인 할 수 있다.
13. `git commit -m "20180604 first TIL"` -> 뭐했는지 메세지 남기는 것이다.
14. `git push`
15. 끝!
