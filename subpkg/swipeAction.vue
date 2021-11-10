<template>
	<view class="container">
		<view class="container-top">
			<view class="title">
				uni-swipe-action 滑动操作
			</view>
			<view class="description">
				SwipeAction 滑动操作操作组件
			</view>
			<view class="author">
				<view class="author-detail">
					作者： DCloud前端团队
				</view>
				<image class="logo-image" src="/static/logo.png"></image>
			</view>
			插件ID：uni-swipe-action <br>
			插件包体积：20.3KB
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
			<view class=" swipe-view">
				<uni-swipe-action>
					<!-- 基础用法 -->
					<uni-swipe-action-item :right-options="options" :left-options="options">
						<view class="swipe-font">SwipeAction 使用场景</view>
					</uni-swipe-action-item>
				</uni-swipe-action>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				options: [{
					text: '取消',
					style: {
						backgroundColor: '#007aff'
					}
				}, {
					text: '确认',
					style: {
						backgroundColor: '#dd524d'
					}
				}]
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

	.swipe-view {
		background-color: #eaedf8;
		display: flex;
		flex-direction: column;
		margin: 10rpx 0;
	}

	.swipe-font {
		display: flex;
		justify-content: center;
		height: 70rpx;
		line-height: 70rpx;
	}
</style>
