---
layout: post
title:  "vue-webpack-less"
date:   2020-07-14 13:19:48 +0800
categories: vuejs

---
# vue-webpack-less#
Vue安装less
# 原代码 #
```javascript
第一步
app.vue中添加
<button @click="fontfam('mnjcd')">改变字体</button>
motheds里添加方法
fontfam(t) {
  		console.log(t);
  		less.modifyVars({
  			"@fontfamily":t
  		})
		document.getElementById('app').style.fontFamily = t
  	},
style部分
<style lang="less">
@fontfamily:'';
@fontFace:"";
@import "../public/font/font.less";

#app {  
  font-family: @fontFace;  
}
</style>

第二步public|font|font.less
@fontfamily:'';
@font-face {
	font-family:@fontfamily;
	src: url('mnjcd.ttf');
	font-weight: normal;
	font-style: normal;
};


```





