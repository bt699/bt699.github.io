---
layout: post
title:  "vue-webpack-less-font"
date:   2020-07-15 13:19:48 +0800
categories: vuejs

---
# vue-webpack-less-font# #
Vue换字体用antdvue组件
# 原代码 #
```javascript
第一步
npm install less less-loader --save-dev
第二步（废弃）
vue.config.js
module.exports = {
  css: {
      loaderOptions: {
        css: {
          // 这里的选项会传递给 css-loader
        },
        postcss: {
          // 这里的选项会传递给 postcss-loader
        },
		sass: {
		        // @/ 是 src/ 的别名
		        // 所以这里假设你有 `src/variables.sass` 这个文件
		        // 注意：在 sass-loader v8 中，这个选项名是 "prependData"
		        // additionalData: `@import "~@/variables.sass"`
		      },
		      // 默认情况下 `sass` 选项会同时对 `sass` 和 `scss` 语法同时生效
		      // 因为 `scss` 语法在内部也是由 sass-loader 处理的
		      // 但是在配置 `prependData` 选项的时候
		      // `scss` 语法会要求语句结尾必须有分号，`sass` 则要求必须没有分号
		      // 在这种情况下，我们可以使用 `scss` 选项，对 `scss` 语法进行单独配置
		scss: {
		        // additionalData: `@import "~@/variables.scss";`
		},
		      // 给 less-loader 传递 Less.js 相关选项
		less:{
		        // http://lesscss.org/usage/#less-options-strict-units `Global Variables`
		        // `primary` is global variables fields name
			// globalVars: {
		 //          primary: '#fff'
		 //    }
		}
      }
    }
};
第三步（废弃）
App.vue中的style里
@import "./common/font/font.css"

报错
 ERROR  Failed to compile with 1 errors                                                                         15:24:54

 error  in ./src/App.vue?vue&type=style&index=0&lang=less&

Module build failed (from ./node_modules/less-loader/dist/cjs.js):



@import "./common/font/font.css"
^
Missing semi-colon or unrecognised media features on import
      Error in F:\2020antd\antdvue\src\App.vue (line 69, column 0)

 @ ./node_modules/vue-style-loader??ref--10-oneOf-1-0!./node_modules/css-loader??ref--10-oneOf-1-1!./node_modules/vue-loader/lib/loaders/stylePostLoader.js!./node_modules/postcss-loader/src??ref--10-oneOf-1-2!./node_modules/less-loader/dist/cjs.js??ref--10-oneOf-1-3!./node_modules/cache-loader/dist/cjs.js??ref--0-0!./node_modules/vue-loader/lib??vue-loader-options!./src/App.vue?vue&type=style&index=0&lang=less& 4:14-416 14:3-18:5 15:22-424
 @ ./src/App.vue?vue&type=style&index=0&lang=less&
 @ ./src/App.vue
 @ ./src/main.js
 @ multi (webpack)-dev-server/client?http://192.168.8.111:8080/sockjs-node (webpack)/hot/dev-server.js ./src/main.js

报错原因是:后面少个分号;
@import "./common/font/font.css";

第四步
Inline JavaScript is not enabled. Is it set in your options?
vue.config.js
module.exports = {
	css:{
		loaderOptions:{
			less:{
				lessOptions:{
					javascriptEnabled:true
				}
			}
		}
	}
}

第五步
"ReferenceError: less is not defined"
main.js
import less from 'less'
Vue.use(less)

第六步
Less has finished and no sheets were loaded
index.html
<link rel="stylesheet/less" type="text/css" href="<%= BASE_URL %>font/font.less">

第七步
app.vue中添加
<button @click="fontfam('mnjcd')">改变字体</button>
motheds里添加方法
fontfam(t){
		  less.modifyVars({
			  "@fontfam":t
		  })
		  document.getElementById('app').style.fontFamily = t
	  }
style部分
<style lang="less">
@fontfam:'';
@import '../public/font/font.less';
#app {
  font-family: @fontfam; 
}
</style>

第八步
public|font|font.less和字体文件mnjcd.ttf
@fontfam:'';
@font-face{
	font-family: @fontfam;
	src:url('mnjcd.ttf')
}
```





