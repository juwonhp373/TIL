# JavaScript 기초5
## TheTheLab Friends 수업
JSON 파일을 이용하여 바뀌는 option마다 그에 맞는 정보들이 화면에 나오도록 만드는게 목적이다.
```JSON
const friends = [  
  {  
    gender: 'female',  
  items: [  
      {  
        year: 2014,  
  items: [  
          {  
            group: 23,  
  items: [  
              {  
                name: '조성현'  
  },  
  {  
                name: '이영주'  
  }  
            ]  
          }  
        ]  
      },  
  {  
        year: 2015,  
  items: [  
          {  
            group: 24,  
  items: [  
              {  
                name: '장한나'  
  }  
            ]  
          },  
  {  
            group: 23,  
  items: [  
              {  
                name: '이은정'  
  }  
            ]  
          }  
        ]  
      },  
  {  
        year: 2016,  
  items: [  
          {  
            group: 22,  
  items: [  
              {  
                name: '이수정'  
  },  
  {  
                name: '임진영'  
  }  
            ]  
          },  
  {  
            group: 21,  
  items: [  
              {  
                name: '홍주원'  
  },  
  {  
                name: '구윤정'  
  }  
            ]  
          }  
        ]  
  
      }  
    ]  
  },  
  {  
    gender: 'male',  
  items: [  
      {  
        year: 2008,  
  items: [  
          {  
            group: 31,  
  items: [  
              {  
                name: '한현우'  
  }  
            ]  
          }  
        ]  
  
      },  
  {  
        year: 2010,  
  items: [  
          {  
            group: 25,  
  items: [  
              {  
                name: '허재종'  
  },  
  {  
                name: '안동참치'  
  }  
            ]  
          }  
        ]  
      },  
  {  
        year: 2014,  
  items: [  
          {  
            group: 24,  
  items: [  
              {  
                name: '홍준엽'  
  },  
  ]  
          }  
        ]  
      },  
  {  
        year: 2015,  
  items: [  
          {  
            group: 23.5,  
  items: [  
              {  
                name: '공현식'  
  },  
  ]  
          }  
        ]  
      },  
  ]  
  }  
]
```
> gender -> admission year -> age -> name
```JavaScript
const filter = ['ALL', 'ALL', 'ALL']  
const $result = $('.friends-field');  
  
$('select').on('change', function () {  
  const index = $this.attr('index') * 1;  
  const $optionSelected = $this.find('option:selected');  
  filter[index] = $optionSelected.text();  
  const names = [];  
  console.log(filter);  
  
  for (var i = 0; i < filter.length; i++) {  
    if (i === 0) {  
      bond = JSON.parse(JSON.stringify(friends));  
  }  
    if (filter[i] === 'ALL') {  
      bond = all(bond);  
  } else {  
      bond = part(bond, i);  
  }  
  }  
  
  for (var i = 0; i < bond.length; i++) {  
    names[i] = bond[i].name  
  }  
  $result.text(names);  
})
```
> pug에서 select tag로 gender, admission year, age순으로 만들어 둔 것을 배열에 넣어서 option이 바뀔 때 마다 배열이 변경되게 할 것이다. 

 `const filter = ['ALL', 'ALL', 'ALL'];`
 -  초기 배열 상태를 지정해 둔 것이다.
 - 함수 안의 지역변수가 아닌 전역변수로 선언 해둔 이유는 지역 변수로 설정 해 둘 경우, 함수가 종료됐을때 변수도 파괴되기 때문에 계속 저장된 내용을 가지고 있을 수 있게 하기 위해서 이다. 

`const $this = $(this);`
- html로 가져온 것을 Jquery로 바꾼 것이다.

for문 안의 `bond = JSON.parse(JSON.stringify(friends));`
 - 계속 이어서 bond가 꾸준히 바뀐 거로 또 돌아야 하기 때문에 bond를 계속 사용 할 수 있도록 시작할 때 bond에 friends를 복사 해 둔다.

```JavaScript
let bond = [];  
  
const all = function (array) {  
  bond = [];  
  let func = JSON.parse(JSON.stringify(array));  
  for (var i = 0; i < func.length; i++) {  
    for (var j = 0; j < func[i].items.length; j++) {  
      bond.push(func[i].items[j]);  
  }  
  }  
  console.log(bond);  
  return bond;  
}  
  
const part = function (array, index) {  
  bond = [];  
  let func = JSON.parse(JSON.stringify(array));  
  for (var i = 0; i < func.length; i++) {    
  if (filter[index].toLowerCase() === func[i][Object.keys(func[i])[0]] + '') {  
      for (var j = 0; j < func[i].items.length; j++) {  
        bond.push(func[i].items[j])  
      }  
    }  
  }  
  console.log(bond);  
  return bond;  
}
```
>option이 'ALL' 일 때와 아닐 때의 함수를 만든다.
### const all
bond는 계속 비워주되, 전에 저장 되어있던 내용들은 계속 사용해야하기 때문에 clone을 떠서 `func`라는 배열에 저장해두고 `func`를 사용한다.

배열의 크기만큼 for문으로 돌리고, 그 배열안에 있는 items를 bond에 저장해야하기 때문에 items의 길이만큼 for문으로 bond에 push해준다.
### const part
배열도 매개변수로 받고, part에는 index도 필요하다.

마찬가지로 bond는 비워주고,`func`를 clone 떠서 사용한다.

배열의 크기만큼 돌고, 돌때 사용자가 변경한 option에 따라 가져와야 하는 부분이 다르기 때문에 if문으로 filter의 바뀐 index의 글자와 JSON의 value값이 같다면 다음 for문으로 갈 수있도록 해야한다.

JSON에서 value가져오는 법
```javascript
func[i][Object.keys(func[i])[0]]
```
이걸 풀어서 생각하면,
```javascript
  var keys = Object.keys(func[i]);  
  var key = keys[0];  
  //func[i][object.keys(func[i])[0]] = func[i][key]
```
이렇게 된다.

