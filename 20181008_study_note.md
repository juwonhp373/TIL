# Asset Bank 1.

## object-fit Property

object-fit 속성은 `img` 와 `video` 가  감싸고 있는 클라스안에서 크기가 어떻게 재정의 되는지 결정하는 것이다.

![Paris](https://www.w3schools.com/css/paris.jpg)
사이즈가 400x300인 `img` 이다.

이 `img` 가 200x400 인 클라스 안에 들어가게 된다면 크기에 맞춰지기 위해 찌그러진 크기로 보이게 될것이다.

만약 여기서 상위 
```sass
object-fit: cover
```
를 사용하면 
`img` 가 200x400 의 공간을 전부 채우려고 측면을 자르고 꽉 채워서 보여줄 것이다.


