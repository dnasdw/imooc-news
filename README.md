# 适配小程序

1. uni.getSystemInfoSync() 的使用方法
2. uni.getMenuButtonBoundingClientRect() 的使用方法
3. 注意自定义导航栏要避开小程序的胶囊按钮
4. h5 端 和 app 端 使用45px 的高度 
5. 其他小程序端，使用计算后的导航栏高度
6. 内容宽度也要根据不同平台特性去计算
7. 使用自定义导航栏，势必用户体验会不太好 ，所以尽量使用原生导航栏去做这些事儿