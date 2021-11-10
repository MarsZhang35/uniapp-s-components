<template>
	<view class="container">
		<view class="container-top">
			<view class="title">
				uni-group 分组 
			</view>
			<view class="description">
				分组组件可用于将组件用于分组，添加间隔，以产生明显的区块
			</view>
			<view class="author">
				<view class="author-detail">
					作者： DCloud前端团队
				</view>
				<image class="logo-image" src="/static/logo.png"></image>
			</view>
			插件ID：uni-group <br>
			插件包体积：3.4KB
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
			<uni-group title="分组1 普通模式" top="20">
			    <view>分组1 的内容</view>
			    <view>分组1 的内容</view>
			</uni-group>
			
			<uni-group title="分组2 card模式" top="20" mode="card">
			    <view>分组2 的内容</view>
			    <view>分组2 的内容</view>
			</uni-group>
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
