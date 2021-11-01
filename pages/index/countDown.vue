<template>
	<view class="container">
		<view class="container-top">
			<view class="title">
				CountDown 倒计时
			</view>
			<view class="description">
				CountDown 倒计时组件
			</view>
			<view class="author">
				<view class="author-detail">
					作者： DCloud前端团队
				</view>
				<image class="logo-image" src="/static/logo.png"></image>
			</view>
			插件ID：CountDown <br>
			插件包体积：5KB
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
			<uni-countdown :day="1" :showColon="showcolon" :splitorColor="splitorcolor" :color="fontColor" :backgroundColor="backColor"
				:show-day="showDay" :hour="2" :minute="60" :second="0"></uni-countdown>
			<uni-section title="是否显示天" type="line"></uni-section>
			<view class="show-day">
				<button class="show-day" @click="showdaies">是否显示天</button>
			</view>
			<uni-section title="随机改变颜色" type="line"></uni-section>
			<view class="change-color">
				<button class="change-color-bgc" @click="changebgc">背景颜色</button>
				<button class="change-font-color" @click="fontsColor">字体颜色</button>
				<button class="change-font-color" @click="splitorsColor">分隔符颜色</button>
			</view>
			<uni-section title="是否以冒号为分隔符" type="line"></uni-section>
			<view class="change-colon-view">
				<button class="change-colon" @click="changeColon">分隔符切换</button>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				showDay: true,
				backColor: "#FFFFFF",
				fontColor: "#000000",
				splitorcolor: "#000000",
				showcolon:"true"
			}
		},
		methods: {
			showdaies() {
				this.showDay = !this.showDay
			},
			changebgc() {
				const rgb = []
				for (let i = 0; i < 3; ++i) {
					let color = Math.floor(Math.random() * 256).toString(16)
					color = color.length == 1 ? '0' + color : color
					rgb.push(color)
				}
				this.backColor = '#' + rgb.join('')
			},
			fontsColor() {
				const rgb = []
				for (let i = 0; i < 3; ++i) {
					let color = Math.floor(Math.random() * 256).toString(16)
					color = color.length == 1 ? '0' + color : color
					rgb.push(color)
				}
				this.fontColor = '#' + rgb.join('')
			},
			splitorsColor() {
				const rgb = []
				for (let i = 0; i < 3; ++i) {
					let color = Math.floor(Math.random() * 256).toString(16)
					color = color.length == 1 ? '0' + color : color
					rgb.push(color)
				}
				this.splitorcolor = '#' + rgb.join('')
			},
			changeColon(){
				this.showcolon = !this.showcolon
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
	
	.change-color{
		display: flex;
		flex-direction: row;
	}
</style>
