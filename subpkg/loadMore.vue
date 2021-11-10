<template>
	<view class="container">
		<view class="container-top">
			<view class="title">
				uni-load-more 加载更多
			</view>
			<view class="description">
				LoadMore 组件，常用在列表里面，做滚动加载使用。
			</view>
			<view class="author">
				<view class="author-detail">
					作者： DCloud前端团队
				</view>
				<image class="logo-image" src="/static/logo.png"></image>
			</view>
			插件ID：uni-load-more <br>
			插件包体积：10.8KB
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
			<uni-load-more :color="color" iconType="auto" :status="status" :contentText="contentText"></uni-load-more>
			<uni-load-more :color="color" iconType="circle" :status="status" :contentText="contentText"></uni-load-more>
			<uni-load-more iconSize="36" :color="color" iconType="snow" :status="status" :contentText="contentText"></uni-load-more>
			<uni-section title="不同状态" type="line"></uni-section>
			<view class="status-view">
				<button class="status" @click="statusm">查看更多</button>
				<button class="status" @click="statusl">加载中</button>
				<button class="status" @click="statuslm">没有更多</button>
			</view>
			<uni-section title="改变颜色" type="line"></uni-section>
			<view class="change-color">
				<button class="change-color" @click="changeColor">改变颜色</button>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				contentText: {
					contentdown: '查看更多',
					contentrefresh: '加载中',
					contentnomore: '没有更多'
				},
				status:"more",
				color:"#777777"

			}
		},
		methods: {
			statusm(){
				this.status = "more"
			},
			statusl(){
				this.status = "loading"
			},
			statuslm(){
				this.status = "nomore"
			},
			changeColor(){
				const rgb = []
				for (let i = 0; i < 3; ++i) {
					let color = Math.floor(Math.random() * 256).toString(16)
					color = color.length == 1 ? '0' + color : color
					rgb.push(color)
				}
				this.color = '#' + rgb.join('')
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
	
	.status-view{
		display: flex;
		flex-direction: row;
	}
</style>
