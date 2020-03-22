# 选项卡数据初始化

出数据初始化的过程 

1. 编写 get_label 云函数，并部署或着上传运行云函数
2. 客户端调用 uniCloud.callfunctions() api ，运行get_label 云函数
3. 云函数运行 完成之后，将数据 return 给客户端
4. 客户端通过 callback 或者 Promise 接受云函数传回来的参数
5. 参数赋值给本地变量 
6. 变量传给 tab 组件 的list 属性
7. tab 组件通过  props 接受 list 参数
8. 最终赋值给元素，进行数据渲染


Tips
- 写完云函数一定不要忘记上传部署或者上传运行，否则云函数不是最新的
- 云函数中 db.collection 后，一定不要忘记 get(),否则不会真正的去请求数据表


