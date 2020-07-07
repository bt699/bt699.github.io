---
layout: post
title:  "修改antdv的table样式用deep"
date:   2020-07-07 13:19:48 +0800
categories: vuejs

---
# 修改antdv的table样式用deep#
用ConfigProvider组件可以添加
# 原代码 #
```javascript
<ConfigProvider :style="{fontSize:fontSize+'px'+' !important',fontSizeBase:fontSize+'px'}">
可以全局添加样式
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



```




