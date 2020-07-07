---
layout: post
title:  "修改Vue的fontSize样式大小修改"
date:   2020-07-06 13:19:48 +0800
categories: vuejs

---
# 修改Vue的fontSize样式大小修改#
用ConfigProvider组件可以添加
# 原代码 #
```javascript
方案一:
<ConfigProvider :style="{fontSize:fontSize+'px'+' !important',fontSizeBase:fontSize+'px'}">
可以全局添加样式
方案二:
<style scoped>
.editable-row-operations a {
  margin-right: 8px;
}
::v-deep .ant-table{
	font-size: 25px;
}
/* /deep/ .ant-table {
     font-size: 25px;
    } */
</style>

方案三:直接操作DOM
<html>
<head>
<script type="text/javascript">
const x = document.getElementsByClassName("ant-tag")
function changefont(item){
	console.log(item)
	   /*   item.forEach(i=>{
			  i.style.fontSize = "25px"
		  }) */
		  for(i=0;i<item.length;i++){
			 //onsole.log(i);
			  item[i].style.fontSize = "25px"
			 //onsole.log(i);
		  }
//tem.style.fontSize = "25px"

}
function setFontSize()
{
document.getElementsByClassName("ant-tag")[0].style.fontSize="25px";
}
</script>
</head>
<body>

<p id="p1" class="ant-tag">This is an example paragraph.</p>
<p id="p1" class="ant-tag">This is an example paragraph.</p>
<p id="p1" class="ant-tag">This is an example paragraph.</p>
<input type="button" onclick="changefont(x)" value="Change font-size" />

</body>
</html>

方案四:
适用开发环境，build编译前设置
/src/theme.js
module.exports = {
	"@font-size-base": "25px",// 主字号
}

方案五(定稿):
   第一步在组件中<a-menu style="font-size:var(--foSize);">增加css变量
   第二步在vars中定义变量--foSize
   /src/styles/vars.less
   @import "~ant-design-vue/lib/style/themes/default.less";
   @import "~ant-design-vue/es/style/color/tinyColor.less";
   @link-color: #00375B;
   @primary-color: #00375B;
   @font-size-base:14px;
   @font-size:14px;
   @font-size-sm: 12px;
   :root {
       --PC: @primary-color;      //color.less中加入css原生变量：--PC
       --foSize: @font-size;
       --fsb:@font-size-base
    }
	第三步vue的methods
	//换字体
	changeFont(size) {
	    console.log(size)
	    console.log(document);
	    //const docEl = document.querySelector("html")
	    //console.log(docEl);
	    document.querySelector("body").style.fontSize = size
	    //console.log(sty);
	    //docEl.head.style.fontSize = size
	      less.modifyVars({
	        "@font-size-base": size,// 主字号
	        "@primary-color": '#000000',
	        "@font-size-sm": size
	      });
	},
	第四步:写按钮
	<a-button type="primary" @click="changeFont(25+'px')">改大小</a-button>
方案六(多窗口组件):
 第一步:组件件上加上style="font-size: var(--fsb);记住size和var之间一定要有空格 
 <a-tabs v-if="multipage" :active-key="activePage" style="font-size: var(--fsb);margin-top: -8px; margin-bottom: 8px" :hide-add="true" type="editable-card" @change="changePage" @edit="editPage">
<style scoped>
::v-deep .ant-tabs-nav-container{
    font-size: var(--fsb);
}
</style>


```



