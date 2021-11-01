<template>
	<view class="container">
		<view class="container-top">
			<view class="title">
				uni-collapse 折叠面板
			</view>
			<view class="description">
				Collapse 组件，可以折叠 / 展开的内容区域。
			</view>
			<view class="author">
				<view class="author-detail">
					作者： DCloud前端团队
				</view>
				<image class="logo-image" src="/static/logo.png"></image>
			</view>
			插件ID：uni-collapse <br>
			插件包体积：9.6KB
			<view class="git-info">
				<image class="git-image" src="/static/git.png"></image>
				<uni-link href="https://github.com/dcloudio/uni-ui" text="https://github.com/dcloudio/uni-ui">
				</uni-link>
			</view>
		</view>
		<view class="container-bottom">
			<view class="title">
				概述
			</view>
			<uni-collapse>
				<uni-collapse-item class="first-collapse" :show-arrow="showArrow" title="默认开启"
					:show-animation="showAnimation" :open="true" thumb="/static/c2.png">
					<text class="first-collapse-font"> 显示内容1</text>
				</uni-collapse-item>
				<uni-collapse-item title="禁用状态" disabled :show-arrow="showArrow">
				</uni-collapse-item>
			</uni-collapse>
			<uni-section title="是否有动画" type="line"></uni-section>
			<view class="">
				<button class="show-animation" @click="showAnimations">是否显示动画</button>
			</view>
			<uni-section title="是否有箭头" type="line"></uni-section>
			<view class="">
				<button class="show-arrow" @click="showArrows">是否显示箭头</button>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				showAnimation: true,
				showArrow: true
			}
		},
		methods: {
			showAnimations() {
				this.showAnimation = !this.showAnimation
			},
			showArrows() {
				this.showArrow = !this.showArrow
			}
		}
	}
</script>

<style>
	.container {
		padding-bottom: 150rpx;
	}

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

	.description {
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.author {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		width: 55%;
	}

	.author-detail {}

	.logo-image {
		width: 40rpx;
		height: 40rpx;
	}

	.git-info {
		display: flex;
		flex-direction: row;
	}

	.git-image {
		width: 40rpx;
		height: 40rpx;
		padding-right: 10rpx;
	}

	.first-collapse-font {
		display: flex;
		justify-content: center;
	}
</style>
