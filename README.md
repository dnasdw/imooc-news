# 使用自定义事件同步数据

1. 使用 uni.$emit() 和 uni.$on() 去做全局的事件监听，改变 tab 的长度
2. 注意：在发生数据变化的时候，要清空之前的缓存数据 listCatchData 和 load 字段 ，避免发生 key 重复，或者有重复数据出现
3. 自定义事件只能在已经打开的页面监听，如果页面没有打开，则用不了  uni.$on() ,它是没有时机去监听事件的。
4. 如果是频发的触发自定义事件，那么需要在合适的时机去销毁事件监听，使用 uni.$off(),避免发生重复监听事件[参考](https://uniapp.dcloud.io/collocation/frame/communication?id=off)
