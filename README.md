# 发布评论页面展示
1. 使用 popup 组件去实现发布弹窗，各种属性 [参考](https://ext.dcloud.net.cn/plugin?id=329)
2. 如果要去操作页面元素，如使用ref属性，或者获取节点信息，应该在 onReady 中去实现，而不是onLoad ，onLoad生命周期 实在页面初始化就会去执行，而 onRead 是在页面渲染完毕去执行的