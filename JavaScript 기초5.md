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
