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
 https://127.0.0.1:5000/updatafont net::ERR_SSL_PROTOCOL_ERROR
 排查原因：https应该是http
 
 POST http://127.0.0.1:5000/updatafont 500 (Internal Server Error)
 排查nodejs问题
 
 TypeError: req.send is not a function
 排查原因：req.send应该是 res.send
 
 RangeError [ERR_HTTP_INVALID_STATUS_CODE]: Invalid status code: {
   res_code: '0',
   type: undefined,
   originalname: 'mnjcd.ttf',
   size: 2973692,
   path: 'C:\\Users\\zrt\\AppData\\Local\\Temp\\1595076252166-mnjcd.ttf'
 }
     at ServerResponse.writeHead (_http_server.js:248:11)
     at ServerResponse._implicitHeader (_http_server.js:239:8)
     at write_ (_http_outgoing.js:650:9)
     at ServerResponse.end (_http_outgoing.js:760:5)
     at ServerResponse.send (F:\2020antd\node\node_modules\express\lib\response.js:221:10)
     at ServerResponse.sendStatus (F:\2020antd\node\node_modules\express\lib\response.js:359:15)
     at F:\2020antd\node\updatafont.js:69:6
     at Layer.handle [as handle_request] (F:\2020antd\node\node_modules\express\lib\router\layer.js:95:5)
     at next (F:\2020antd\node\node_modules\express\lib\router\route.js:137:13)
     at Immediate._onImmediate (F:\2020antd\node\node_modules\multer\lib\make-middleware.js:53:37)
排查原因：window没有temp写入权限 ,根本原因desination应该是destination

postman 如何上传文件
答：选择Body--->form-data--->key里选file--->value里可以选择文件

MulterError: Unexpected field
    at wrappedFileFilter (F:\2020antd\node\node_modules\multer\index.js:40:19)
    at Busboy.<anonymous> (F:\2020antd\node\node_modules\multer\lib\make-middleware.js:114:7)
    at Busboy.emit (events.js:310:20)
    at Busboy.emit (F:\2020antd\node\node_modules\busboy\lib\main.js:38:33)
    at PartStream.<anonymous> (F:\2020antd\node\node_modules\busboy\lib\types\multipart.js:213:13)
    at PartStream.emit (events.js:310:20)
    at HeaderParser.<anonymous> (F:\2020antd\node\node_modules\dicer\lib\Dicer.js:51:16)
    at HeaderParser.emit (events.js:310:20)
    at HeaderParser._finish (F:\2020antd\node\node_modules\dicer\lib\HeaderParser.js:68:8)
    at SBMH.<anonymous> (F:\2020antd\node\node_modules\dicer\lib\HeaderParser.js:40:12)
	
	排查原因：key不一致造成的，postman里的key应与node里upload.single里的值一样才行。
	//app.post('/updatafont',upload.single('file'),function(req,res,next){
		
		
	Error: ENOENT: no such file or directory, open 'F:\2020antd\node\upload\1595079735954-mnjcd.ttf'
	排查原因：没有文件夹upload
	
	RangeError [ERR_HTTP_INVALID_STATUS_CODE]: Invalid status code: {
	  res_code: '200',
	  type: undefined,
	  originalname: 'mnjcd.ttf',
	  size: 2973692,
	  path: 'upload\\1595082272921-mnjcd.ttf'
	}
	    at ServerResponse.writeHead (_http_server.js:248:11)
	    at ServerResponse._implicitHeader (_http_server.js:239:8)
	    at write_ (_http_outgoing.js:650:9)
	    at ServerResponse.end (_http_outgoing.js:760:5)
	    at ServerResponse.send (F:\2020antd\node\node_modules\express\lib\response.js:221:10)
	    at ServerResponse.sendStatus (F:\2020antd\node\node_modules\express\lib\response.js:359:15)
	    at F:\2020antd\node\updatafont.js:71:6
	    at Layer.handle [as handle_request] (F:\2020antd\node\node_modules\express\lib\router\layer.js:95:5)
	    at next (F:\2020antd\node\node_modules\express\lib\router\route.js:137:13)
	    at Immediate._onImmediate (F:\2020antd\node\node_modules\multer\lib\make-middleware.js:53:37)
		
	排查原因：res.sendStatus应该是res.send
		
		提交以后一直转圈。
		排查原因：if(file.mimetype === 'applicatin/x-font-ttf'){应该是console.log(file.mimetype == 'font/ttf');
```





