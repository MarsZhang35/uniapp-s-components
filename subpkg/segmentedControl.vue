<template>
	<view class="container">
		<view class="container-top">
			<view class="title">
				uni-segmented-control 分段器
			</view>
			<view class="description">
				分段器由至少 2 个分段控件组成，用作不同视图的显示
			</view>
			<view class="author">
				<view class="author-detail">
					作者： DCloud前端团队
				</view>
				<image class="logo-image" src="/static/logo.png"></image>
			</view>
			插件ID：uni-segmented-control <br>
			插件包体积：3.8KB
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
			<view>
				<uni-segmented-control :activeColor="activeColor" :current="current" :values="items"
					@clickItem="onClickItem" :styleType="styleType"></uni-segmented-control>
				<view class="content">
					<view v-show="current === 0">
						选项卡1的内容
					</view>
					<view v-show="current === 1">
						选项卡2的内容
					</view>
					<view v-show="current === 2">
						选项卡3的内容
					</view>
				</view>
				<uni-section title="style" type="line"></uni-section>
				<view class="change-style-view">
					<button class="change-style" @click="changeText">文字</button>
					<button class="change-style" @click="changeButton">按钮</button>
				</view>
				<uni-section title="背景色" type="line"></uni-section>
				<view class="change-bgc">
					<button class="change-bgc" @click="changeBgc">改变颜色</button>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				items: ['选项卡1', '选项卡2', '选项卡3'],
				current: 0,
				activeColor: "#007aff",
				styleType:"button"
			}
		},
		methods: {
			onClickItem(e) {
				if (this.current !== e.currentIndex) {
					this.current = e.currentIndex
				}
			},
			changeText(){
				this.styleType = "text"
			},
			changeButton(){
				this.styleType = "button"
			},
			changeBgc() {
				const rgb = []
				for (let i = 0; i < 3; ++i) {
					let color = Math.floor(Math.random() * 256).toString(16)
					color = color.length == 1 ? '0' + color : color
					rgb.push(color)
				}
				this.activeColor = '#' + rgb.join('')
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
	
	.change-style-view{
		display: flex;
		flex-direction: row;
	}
</style>
