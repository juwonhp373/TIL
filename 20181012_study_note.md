# While Working on Asset Bank (WWAB)

## router

```js
import TestDownloadList from '../page/test/download-list/download-list';

export default new Router({  
  mode: 'history',  
  routes: [  
 {  path: '/test/download-list', // 주소 
	name: 'test-download-list',  // URL 주소 말고 다른 방법으로 접근
	component: TestDownloadList  // import 가져옴
    },
  ]
});
```
