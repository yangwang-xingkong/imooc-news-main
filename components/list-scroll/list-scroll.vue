<template>
	<view class="scroll">
		<scroll-view class="list-scroll" scroll-y @scrolltolower="loadmore">
			<!-- 滚动标签内部的滚动元素建议使用一个父标签包裹，避免无法滚动或样式问题 -->
			<view>
				<slot></slot>
			</view>
		</scroll-view>
	</view>
</template>

<script>
	export default {
		name: "list-scroll",
		data() {
			return {

			};
		},
		methods:{
			loadmore() {
				this.$emit('loadmore')
			}
		}
	}
</script>

<style lang="scss">
	.scroll {
		flex: 1;
		height: 100%;
		overflow: hidden;
		box-sizing: border-box;
		.list-scroll {
			height: 100%;
			display: flex;
			flex-direction: column;
		}
	}
</style>
