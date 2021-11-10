<template>
	<view class="container">
		<view class="container-top">
			<view class="title">
				uni-number-box 数字输入框
			</view>
			<view class="description">
				NumberBox 带加减按钮的数字输入框组件，用户可以控制每次点击增加的数值，支持小数。
			</view>
			<view class="author">
				<view class="author-detail">
					作者： DCloud前端团队
				</view>
				<image class="logo-image" src="/static/logo.png"></image>
			</view>
			插件ID：uni-fav <br>
			插件包体积：4.6KB
			<view class="git-info">
				<image class="git-image" src="/static/git.png"></image>
				<uni-link href="https://github.com/dcloudio/uni-ui" text="https://github.com/dcloudio/uni-ui">
				</uni-link>
			</view>
		</view>
		<view class="container-bottom-view">
			<view class="title">
				概述
			</view>
			<uni-section title="基本引用" type="line"></uni-section>
			<uni-number-box />
			<uni-section title="最小是2 最大是7 初始值是4" type="line"></uni-section>
			<uni-number-box :min="2" :max="7" :value="4" />
			<uni-section title="每次增常和减少0.1" type="line"></uni-section>
			<uni-number-box :step="0.1" />
			<uni-section title="不可更改" type="line"></uni-section>
			<uni-number-box :disabled="true" />
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {

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
</style>
