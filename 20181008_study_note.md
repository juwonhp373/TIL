# Asset Bank 1.

## object-fit Property

object-fit 속성은 `img` 와 `video` 가  감싸고 있는 클라스안에서 크기가 어떻게 재정의 되는지 결정하는 것이다.

![Paris](https://www.w3schools.com/css/paris.jpg)
사이즈가 400x300인 `img` 이다.

이 `img` 가 200x400 인 클라스 안에 들어가게 된다면 크기에 맞춰지기 위해 찌그러진 크기로 보이게 될것이다.
![Paris](https://i.postimg.cc/FH7vyCSS/2018-10-09_12.08.20.png)

만약 여기서 상위 
```sass
object-fit: cover
```
를 사용하면 
`img` 가 200x400 의 공간을 전부 채우려고 측면을 자르고 꽉 채워서 보여줄 것이다.
내용이 종횡비를 유지하면서 정의된 너비와 높이를 가득 채울때까지 확대된다.  
![Paris](https://i.postimg.cc/Ss7bSwBB/2018-10-09_12.08.35.png)

### fill
대체되는 요소의 내용이 지정된 너비와 높이에 따라 크기가 확대(scale up) 혹은 축소(down), 늘어나거나(stretch) 움츠러든다(shrunk). 요소를 가득 채울수 있는 크기로 변화되면서 종횡비는 유지되지 않는다. 이것은 일반적으로 이미지에 강제로 너비와 높이를 지정하는 것과 같다.
```sass
object-fit: fill // default
```
![Paris](https://i.postimg.cc/66cxDxLR/2018-10-09_12.27.18.png)

### contain
내용이 종횡비를 유지하면서 요소에 정의된 너비와 높이안에서 가능한한 많이 확대(scale up)시킨다.  
```sass
object-fit: contain // img 자신의 사이즈를 유지하면서 공간을 전부 채우려고 한다.
```
![Paris](https://i.postimg.cc/mDGGGb53/2018-10-09_12.27.47.png)

### none
내용의 크기가 요소의 크기와는 상관없이 기본 알고리즘에 의해 조정된다. 이 알고리즘은 원본의 크기에 가운데 정렬된 형태를 띈다.  
```sass
object-fit: none // 지정해준 크기를 무시하고 img 본연의 사이즈 그대로 나옴
```
![Paris](https://i.postimg.cc/prsN8KXk/2018-10-09_12.29.03.png)

### scale-down
내용의 크기를 아무것도 지정되지 않거나 혹은 `contain` 이 지정되어 있는 것처럼 변경한다. 이는 원본 크기보다 작아지는 결과를 보여준다.  
```sass
object-fit: scale-down // `contain` 과 `none` 으로 지정된 것처럼 나온다. 원본보다 작은 사이즈로 나오게된다.
```
![Paris](https://i.postimg.cc/mDGGGb53/2018-10-09_12.27.47.png)