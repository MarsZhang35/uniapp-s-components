<template>
	<view class="container-top">
		<view class="title">
			view 视图容器
		</view>
		<view class="description">
			它类似于传统html中的div，用于包裹各种元素内容。
		</view>
		<uni-section class="line" title="实操" type="line"></uni-section>
		<view class="uni-view">
			<view class="uni-view-row">
				flex-direction: row
				<text>\n横向布局</text>
			</view>
			<view class="uni-flex-row">
				<view class="flex-item-red">A</view>
				<view class="flex-item-green">B</view>
				<view class="flex-item-blue">C</view>
			</view>
			<view class="uni-view-column">
				flex-direction: column
				<text>\n纵向布局</text>
			</view>
			<view class="uni-flex-column">
				<view class="flex-item-red">A</view>
				<view class="flex-item-green">B</view>
				<view class="flex-item-blue">C</view>
			</view>
			<view class="uni-scroll">
				Vertical Scroll
				<text>\n纵向滚动</text>
			</view>
			<view>
				<scroll-view class="scroll-Y" :scroll-top="scrollTop" scroll-y="true" @scrolltoupper="upper"
					@scrolltolower="lower" @scroll="scroll">
					<view class="flex-item-red">A</view>
					<view class="flex-item-green">B</view>
					<view class="flex-item-blue">C</view>
				</scroll-view>
			</view>
			<view @tap="goTop" class="link-to-top">
				点击这里返回顶部
			</view>
			<view>
				<scroll-view class="scroll-x" scroll-x="true" @scroll="scroll" :scroll-left="scrollLeft">
					<view id="demo1" class="flex-item-red">A</view>
					<view id="demo2" class="flex-item-green">B</view>
					<view id="demo3" class="flex-item-blue">C</view>
				</scroll-view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				scrollTop: 0,
				old: {
					scrollTop: 0,
					scrollLeft: 0
				},
				scrollLeft: 0,
			}
		},
		methods: {
			upper: function(e) {
				console.log(e)
			},
			lower: function(e) {
				console.log(e)
			},
			scroll: function(e) {
				console.log(e)
				this.old.scrollTop = e.detail.scrollTop
				this.old.scrollLeft = e.detail.scrollLeft
			},
			goTop: function(e) {
				this.scrollTop = this.old.scrollTop
				this.$nextTick(() => {
					this.scrollTop = 0
				});
				uni.showToast({
					icon: "none",
					title: "纵向滚动 scrollTop 值已被修改为 0"
				})
			}
		}
	}
</script>

<style>
	.container-top {
		display: flex;
		justify-content: center;
		align-items: flex-start;
		flex-direction: column;
		padding: 20rpx;
	}

	.title {
		width: 100%;
		font-size: 50rpx;
		font-weight: bold;
		background-color: #6fdbdd;
		display: flex;
		justify-content: center;
		align-items: flex-start;
	}

	.line {
		width: 100%;
	}

	.uni-view {
		width: 100%;
	}

	.uni-flex-row {
		display: flex;
		flex-direction: row;
		width: 100%;
		height: 200rpx;
	}

	.flex-item-red {
		height: 200rpx;
		display: flex;
		justify-content: center;
		align-items: center;
		flex: 1;
		background-color: #f34a4e;
		color: #FFFFFF;
	}

	.flex-item-green {
		height: 200rpx;
		display: flex;
		justify-content: center;
		align-items: center;
		flex: 1;
		background-color: #2eb208;
		color: #FFFFFF;
	}

	.flex-item-blue {
		height: 200rpx;
		display: flex;
		justify-content: center;
		align-items: center;
		flex: 1;
		background-color: #2160ff;
		color: #FFFFFF;
	}

	.uni-flex-column {
		display: flex;
		flex-direction: column;
		height: 600rpx;
	}

	.scroll-Y {
		height: 200rpx;
	}

	.scroll-x {
		height: 200rpx;
		display: flex;
		flex-direction: row;
		white-space: nowrap;
	}

	#demo1 {
		display: inline-block;
		width: 100%;
		height: 140px;
	}

	#demo2 {
		display: inline-block;
		width: 100%;
		height: 140px;
	}

	#demo3 {
		display: inline-block;
		width: 100%;
		height: 140px;
	}
</style>
