<template>
	<swiper class="home-swiper" :current="activeIndex" @change="change">
		<swiper-item v-for="(item ,index) in tab" :key="index" class="swiper-item">
			<list-item :list="listCatchData[index]"></list-item>
		</swiper-item>

	</swiper>
</template>

<script>
	import listItem from './list-item.vue'
	export default {
		components: {
			listItem
		},
		props: {
			tab: {
				type: Array,
				default () {
					return []
				}
			},
			activeIndex: {
				type: Number,
				default: 0
			}
		},
		data() {
			return {
				list: [],
				// js 的限制 listCatchData[index] = data
				listCatchData: {
					0:[],
					1:[]
				}
			};
		},
		watch:{
			tab(newVal){
				if(newVal.length === 0) return
				this.getList(this.activeIndex)
			}
		},
		// onLoad 在页面 ，created 组件
		created() {
			// TODO tab 还没有赋值
			// this.getList(0)
		},
		methods: {
			change(e) {
				const {
					current
				} = e.detail
				console.log(this.tab[current].name);
				this.getList(current)
				this.$emit('change', current)
			},
			getList(current) {
				console.log(this.tab);
				this.$api.get_list({
					name: this.tab[current].name
				}).then(res => {
					console.log(res);
					const {
						data
					} = res
					console.log('请求数据：', data);
					// this.list = data
					// this.listCatchData[current] = data
					// 懒加载
					this.$set(this.listCatchData,current,data)
				})
			}
		}
	}
</script>

<style lang="scss">
	.home-swiper {
		height: 100%;

		.swiper-item {
			height: 100%;
			overflow: hidden;

			.list-scroll {
				height: 100%;
			}
		}
	}
</style>
