<template>
	<swiper class="home-swiper" :current="activeIndex" @change="change">
		<swiper-item v-for="(item ,index) in tab" :key="index" class="swiper-item">
			<list-item :list="list"></list-item>
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
				list: []
			};
		},
		// onLoad 在页面 ，created 组件
		created() {
			this.getList()
		},
		methods: {
			change(e) {
				const {
					current
				} = e.detail
				// console.log(e);
				this.$emit('change', current)
			},
			getList() {
				this.$api.get_list().then(res => {
					console.log(res);
					const {data} = res
					this.list = data
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
