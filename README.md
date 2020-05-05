# 个人中心数据处理
- 云函数直接通过 doc 获取 某一个_id 的用户信息
- 在 app.vue 里获取用户信息，保存到 vuex 里
- vuex 保存用户信息需要使用 uni.setStorageSync / uni.getStorageSync 进行本地化持久储存
- 在 https.js 中使用全局保存的用户id来获取数据