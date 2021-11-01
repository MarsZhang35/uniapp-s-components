<template>
	<view class="container">
		<view class="container-top">
			<view class="title">
				uni-pagination 分页器
			</view>
			<view class="description">
				Pagination 分页器组件，用于展示页码、请求数据等。
			</view>
			<view class="author">
				<view class="author-detail">
					作者： DCloud前端团队
				</view>
				<image class="logo-image" src="/static/logo.png"></image>
			</view>
			插件ID：uni-pagination <br>
			插件包体积：6.4KB
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
			<uni-pagination :current="current" :total="total" :show-icon="showicon" @change="change" />
			<text>当前页：{{ current }}，数据总量：{{ total }}条，每页数据：{{ pageSize }}</text>
			<button type="primary" @click="add">增加</button>
			<button type="default" @click="reset">重置数据</button>
			<uni-section title="切换" type="line"></uni-section>
			<view class="change-view">
				<button class="change" @click="changeIcon">切换图标</button>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				showicon: "true",
				current: 1,
				total: 0,
				pageSize: 10
			}
		},
		methods: {
			changeIcon() {
				this.showicon = !this.showicon
			},
			add() {
				this.total += 10;
			},
			reset() {
				this.total = 0;
				this.current = 1;
			},
			change(e) {
				this.current = e.current;
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
</style>
