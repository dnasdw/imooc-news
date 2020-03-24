# 选项卡与内容联动

1. tab 组件通过 this.$emit() 把当前的一个下标传递页面，页面通知 list 组件tab组件变化了，同时 list 组件接受到tab的值后，通过 curent 属性去改变 swiper 的位置
3. swiper 通过 change 事件获取当前 swiper 的下标，并通过 this.$emit() 把下标传递给页面，页面通知 tab 组件 swiper 变化了，同时 tab 组件改变自己的下标，完成改变
4. 当tab组件改变了 swiper 的current 属性后，swiper改变了，所以又会触发 change 事件，同时把改变后的 current 传递给 tab组件 ，就可以达成 两个组件之间的互动

