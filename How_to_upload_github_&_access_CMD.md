# github 에 push 하는 법

*git remote add origin 'https://github.com/juwonhp373/vue-router-test.git'
-> 이게 뭐지?

cd ..
-> 한단계 외부 파일로 나가는 것.

cd Develop 으로 Develop 에 들어가서,

1. git clone 'https://github.com/juwonhp373/TIL'
   -> 올릴 github 의 주소를 복붙해서 clone 을 뜬다.
2. ls
   -> 해보면 TIL 이라는 폴더가 생겼음을 확인할 수 있다.

3. TIL 폴더에 내가 업로드 하려는 파일을 드래그해 넣는다.

4. cd TIL
5. open .
   -> TIL 폴더를 Finder 에서 열어주는 것.
6. git status
   -> 현재 git 에 push 되지 않은 파일을 보여준다.
7. git add .
8. git commit -m "원하는 메세지 쓰기"
9. git push


# CMD접속

mkdir로 OOO라는 파일을 생성
cd OOO로 파일 안으로 접속
express -v pug -c sass 로 파일?들 다운.
-v [VIEW MODE]
-c [STYLE MODE]
npm install
WebStorm 열기
File 에서 Open들어가서 내가 방금 만든 OOO 디렉토리 찾아서 열기.
app.js에 있는
app.use(’/’, indexRouter); 를 이용해서 주소 경로를 알아 볼 것이다.

'/'부분을 내가 원하는 경로 이름으로 바꿔 준다.
-> '/test’라고 했다.

여기서 7)의 indexRouter는 위의
var IndexRouter = require(’./routes/index’);
을 보아 routes파일에 있는 index파일에 접근할 것으로 보인다.

따라서, routes파일에 index.js 에서
router.get(’/juwon’, function(req, res, next) {
res.send(‘HELLO!!!’);
});

이렇게 추가 한다.

왼쪽 밑에 있는 npm으로 start를 하고 chrome 주소창에
http://127.0.0.1:3000/test/juwon
하면 화면에 ‘HELLO!!!’ 가 나온다.
