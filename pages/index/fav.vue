<template>
	<view class="container">
		<view class="container-top">
			<view class="title">
				uni-fav 收藏按钮
			</view>
			<view class="description">
				Fav 收藏组件，可自定义颜色、大小。
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
			<view class="fav-view">
				<uni-fav class="fav" :circle="circle" :fgColorChecked="fgColorChecked" :fgColor="fgColor"
					:bgColorChecked="bgColorChecked" :bgColor="bgColor" :star="star" :checked="checked"
					@click="onClick" />
			</view>
			<uni-section title="是否显示星星(只在未收藏时生效)" type="line"></uni-section>
			<view class="show-star">
				<button class="show-star" @click="showStar">是否显示星星</button>
			</view>
			<uni-section title="背景色" type="line"></uni-section>
			<view class="change-bgc">
				<button class="change-bgc" @click="changeBgc">未收藏时背景色</button>
				<button class="change-bgc" @click="changesBgc">已收藏时背景色</button>
			</view>
			<uni-section title="字体颜色" type="line"></uni-section>
			<view class="change-bgc">
				<button class="change-bgc" @click="changefgc">未收藏时字体颜色</button>
				<button class="change-bgc" @click="changesfgc">已收藏时字体颜色</button>
			</view>
			<uni-section title="是否显示圆角" type="line"></uni-section>
			<view class="change-circle">
				<button class="change-circle" @click="changeCircle">是否显示圆角</button>
			</view>
			<uni-section title="自定义文字" type="line"></uni-section>
			<view class="fav-view">
				<uni-fav :contentText="contentText" :checked="checked" @click="onClick" />
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				checked: false,
				star: true,
				bgColor: "#eeeeee",
				bgColorChecked: "#007aff",
				fgColor: "#666666",
				fgColorChecked: "#FFFFFF",
				circle: false,
				contentText: {
					contentDefault: '订阅',
					contentFav: '已订阅'
				}
			}
		},
		methods: {
			onClick() {
				this.checked = !this.checked
			},
			showStar() {
				this.star = !this.star
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
			changesBgc() {
				const rgb = []
				for (let i = 0; i < 3; ++i) {
					let color = Math.floor(Math.random() * 256).toString(16)
					color = color.length == 1 ? '0' + color : color
					rgb.push(color)
				}
				this.bgColorChecked = '#' + rgb.join('')
			},
			changefgc() {
				const rgb = []
				for (let i = 0; i < 3; ++i) {
					let color = Math.floor(Math.random() * 256).toString(16)
					color = color.length == 1 ? '0' + color : color
					rgb.push(color)
				}
				this.fgColor = '#' + rgb.join('')
			},
			changesfgc() {
				const rgb = []
				for (let i = 0; i < 3; ++i) {
					let color = Math.floor(Math.random() * 256).toString(16)
					color = color.length == 1 ? '0' + color : color
					rgb.push(color)
				}
				this.fgColorChecked = '#' + rgb.join('')
			},
			changeCircle() {
				this.circle = !this.circle
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

	.fav-view {
		display: flex;
		justify-content: center;
		align-content: space-around;
		padding: 20rpx;
	}

	.change-bgc {
		display: flex;
		flex-direction: row;
	}
</style>
