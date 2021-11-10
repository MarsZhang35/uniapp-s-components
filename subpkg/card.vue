<template>
	<view class="container">
		<view class="container-top">
			<view class="title">
				uni-card 卡片
			</view>
			<view class="description">
				Card 组件，提供常见的卡片样式。
			</view>
			<view class="author">
				<view class="author-detail">
					作者： DCloud前端团队
				</view>
				<image class="logo-image" src="/static/logo.png"></image>
			</view>
			插件ID：uni-card <br>
			插件包体积：5.5KB
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
			<uni-card class="card-view" title="标题文字" thumbnail="/static/c1.png" :mode="modeStyle"
				:is-shadow="iShadow" :extra="moreInfo" note="这是提醒">
				这是内容
			</uni-card>
			<uni-section title="改变阴影" type="line"></uni-section>
			<view class="change-shadow-view">
				<button class="change-shadow" @click="ShadowChange">改变阴影</button>
			</view>
			<uni-section title="改变样式" type="line"></uni-section>
			<view class="change-style">
				<button class="changestyle-to-pic" @click="changetopic">图文卡片</button>
				<button class="changestyle-to-tit" @click="changetotit">标题卡片</button>
				<button class="changestyle-to-bas" @click="changetobas">基础卡片</button>
			</view>
			<!-- <uni-section title="显示更多信息和提示" type="line"></uni-section>
			<view class="diappear">
				<button class="extra-disappear" @click="extraDisappear">隐藏/显示更多信息</button>
				<button class="note-disappear" @click="noteDisappear">标题隐藏/显示提示</button>
			</view> -->
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				iShadow: false,
				modeStyle: "basic",
				moreInfo: "这里有更多信息"
			}
		},
		methods: {
			ShadowChange() {
				this.iShadow = !this.iShadow
			},
			changetopic() {
				this.modeStyle = "style"
			},
			changetotit() {
				this.modeStyle = "title"
			},
			changetobas() {
				this.modeStyle = "basic"
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

	.change-style {
		display: flex;
		flex-direction: row;
	}

	.diappear {
		display: flex;
		flex-direction: row;
	}

	
</style>
