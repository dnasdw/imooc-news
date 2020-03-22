<template>
	<view class="home">
		<!-- 自定义导航栏 -->
		<navbar></navbar>
		<tab :list="tabList"  @tab="tab"></tab>
		
		<list-scroll>
			<list-card mode="base"></list-card>
			<list-card mode="image"></list-card>
			<list-card mode="column"></list-card>
		</list-scroll>
	</view>
</template>

<script>
	// easyCom components/组件名/组件名.vue 局部引入
	export default {
		data() {
			return {
				title: 'Hello',
				tabList: []
			}
		},
		onLoad() {
			this.getLabel()
		},
		methods: {
			tab({data,index}){
				console.log(data,index);
			},
			getLabel() {
				// 调用云函数方法
				this.$api.get_label({
					name: 'get_label'
				}).then((res) => {
					const {
						data
					} = res
					this.tabList = data
					// 	console.log(this.tabList);
				})

			}
		}
	}
</script>

<style lang="scss">
	page {
		height: 100%;
		display: flex;
	}
	.home  {
		display: flex;
		flex-direction: column;
		flex: 1;
		border: 1px red solid;
		overflow: hidden;
	}
</style>
