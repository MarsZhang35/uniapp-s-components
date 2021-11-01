<template>
	<view class="container">
		<view class="container-top">
			<view class="title">
				uni-search-bar 搜索栏
			</view>
			<view class="description">
				搜索栏组件，通常用于搜索商品、文章等
			</view>
			<view class="author">
				<view class="author-detail">
					作者： DCloud前端团队
				</view>
				<image class="logo-image" src="/static/logo.png"></image>
			</view>
			插件ID：uni-search-bar <br>
			插件包体积：6KB
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
			<!-- 基本用法 -->
			<uni-search-bar :bgColor="bgColor" @confirm="search" placeholder="请输入搜索内容"></uni-search-bar>

			<!-- v-model 用法 -->
			<uni-search-bar :bgColor="bgColor" placeholder="请输入搜索内容" @confirm="search" :focus="true" v-model="searchValue"
				@cancel="cancel" @clear="clear"></uni-search-bar>
			<view class="">
				当前输入为：{{searchValue}}
			</view>
			<!-- 设置圆角 -->
			<uni-search-bar :bgColor="bgColor" placeholder="自定义图标" :radius="100" @confirm="search">
				<uni-icons slot="searchIcon" color="#999999" size="18" type="home" />
			</uni-search-bar>
			<uni-section title="背景色" type="line"></uni-section>
			<view class="change-bgc">
				<button class="change-bgc" @click="changeBgc">改变背景颜色</button>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				searchValue: '123123',
				bgColor:"#F8F8F8"
			}
		},
		methods: {
			search(res) {
				uni.showToast({
					title: '搜索：' + res.value,
					icon: 'none'
				})
			},
			clear(res) {
				uni.showToast({
					title: 'clear事件，输入值为：' + res.value,
					icon: 'none'
				})
			},
			cancel(res) {
				uni.showToast({
					title: '点击取消，输入值为：' + res.value,
					icon: 'none'
				})
			},
			changeBgc() {
				const rgb = []
				for (let i = 0; i < 3; ++i) {
					let color = Math.floor(Math.random() * 256).toString(16)
					color = color.length == 1 ? '0' + color : color
					rgb.push(color)
				}
				this.bgColor = '#' + rgb.join('')
			},
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
