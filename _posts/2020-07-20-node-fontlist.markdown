---
layout: post
title:  "node-multer"
date:   2020-07-15 13:19:48 +0800
categories: nodejs

---
# node-multer #
npm i multer -s
# 原代码 #
```javascript
(node:13204) UnhandledPromiseRejectionWarning: ReferenceError: fs is not defined
排查原因:添加const fs = require('fs')

(node:10504) UnhandledPromiseRejectionWarning: Error: ENOENT: no such file or directory, scandir 'F:\2020antd\font'

排查原因:let root = path.resolve(__dirname,'../upload')应该是路径问题let root = path.resolve(__dirname,'./upload')

(node:3892) UnhandledPromiseRejectionWarning: TypeError: Cannot set property 'body' of undefined
排查原因:注销掉body部分
// ctx.body = {
	// 	code:200,
	// 	message:'获取成功',
	// 	data:arr
	// }
	
//console.log('79',list);
直接打印显示是Promise { <pending> }

排查原因：用then回调
font().then(v=>{
	   console.log('77',v);
	   res.send(v)
   })
   //console.log('79',list); 完美
```





