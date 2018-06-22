### CSS 선택자
>[Rule Set]
```CSS
p{color: red; padding: 5px;}
```
- `p` - 선택자(selector)
- `color` - 속성(property)
- `red` - 속성값(property-value)
- `color: red;` , `padding: 5px;` - 선언(Declaration)
- `color: red; padding: 5px;` - 선언 블록 (Declaration block)
#### Rule Set
Rule Set(Rule)은 HTML페이지 안의 특정 요소들을 어떻게 Rendering 할 것인지 브라우저에게 알려주는 CSS 문장이다.

스타일 규칙이라고도 불린다.
#### 선택자(Selector)
왼쪽 중괄호 "{" 가 나오기 전의 부분 모두가 선택자 이다.

선택자는 Rule Set의 영향을 받는 HTML페이지 안의 특정 element들을 선택해서 선언블록(Declaration Block)의 내용을 적용시켜 준다.

#####  *예외
```CSS
@media print {background-color: transparent;} 
```
위처럼 "@" 키워드로 시작하는 문장은 Rule Set이 아닌 At-Rule이기 때문에 위 문장에서의 중괄호 전 부분은 선택자가 아니다.
### 선택자(Selector)의 종류
#### 전체 선택자(Universal Selector)
#### 태그 선택자(Type Selector)
#### 클래스 선택자(Class Selector)
#### ID 선택자(ID Selector)
#### 복합 선택자(Combinator)
#### 속성 선택자(Attribute Selectors)
#### 가상 클래스 선택자(Pseudo-Classes)
#### etc
