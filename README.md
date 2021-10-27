## 前端vue项目中使用sql-formatter结合codemirror实现sql编辑器中的SQL代码格式化功能、自动匹配大小写功能、高亮功能

主要实现的功能就是SQL编辑器，可以让SQL代码实现格式化代码、自动匹配大小写、高亮等功能
### 详文可参考：https://blog.csdn.net/weixin_45851208/article/details/105118847

### 使用方法：

``` bash
下载node_model文件：npm install

# 本地运行项目
npm run dev

# 打包项目
npm run build
```

### 可能出现的报错问题及解决方法：

1.vue.esm.js?efeb:628 [Vue warn]: Error in v-on handler: “TypeError: Cannot read properties of undefined (reading ‘format’)”。
解决方案：（1）降低版本，降至3.0或者2.0

2.光标一直处于中间位置，出现这个问题还是需要检查大家自己的样式问题。本身它的封装是靠左显示的。

最终效果：
![image](https://user-images.githubusercontent.com/19965530/139035191-bf81ab65-7ff7-4208-8921-b58ba2f8c764.png)

