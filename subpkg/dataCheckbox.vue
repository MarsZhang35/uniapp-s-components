<template>
	<view class="container">
		<view class="container-top">
			<view class="title">
				uni-data-checkbox 数据选择器
			</view>
			<view class="description">
				通过数据驱动的单选框和复选框
			</view>
			<view class="author">
				<view class="author-detail">
					作者： DCloud前端团队
				</view>
				<image class="logo-image" src="/static/logo.png"></image>
			</view>
			插件ID：uni-data-checkbox <br>
			插件包体积：9.5KB
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
			<uni-data-checkbox :selectedTextColor="selectedTextcolor" :icon="iCon" :mode="modes"
				:selectedColor="selectedcolor" :multiple="multipleChange" v-model="valueS" :localdata="range">
			</uni-data-checkbox>
			<uni-section title="改变字体颜色" type="line"></uni-section>
			<view class="font-color">
				<button class="font-color" @click="fontColor">换字体颜色</button>
			</view>
			<uni-section title="切换单/多选" type="line"></uni-section>
			<view class="multipleChange-view">
				<button class="multipleChange" @click="multiplesChange">切换单/多选</button>
			</view>
			<uni-data-checkbox :selectedTextColor="selectedTextcolor" :icon="iCon" :mode="modes"
				:selectedColor="selectedcolor" :multiple="multipleChange" v-model="valueS" :localdata="range">
			</uni-data-checkbox>
			<uni-section title="改变mode" type="line"></uni-section>
			<view class="change-mode">
				<button class="change-button" @click="changetoButton">Button模式</button>
				<button class="change-tag" @click="changetoTag">Tag模式</button>
				<button class="change-default" @click="changetoDefault">Default模式</button>
			</view>
			<uni-section title="List模式下" type="line"></uni-section>
			<view class="list-view">
				<button class="change-mode" @click="changetoList">List模式</button>
				<button class="change-icon" @click="changetoIcon"> icon显示右边</button>
				<button class="change-icon" @click="changetoICon"> icon显示左边</button>
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
				multipleChange: false,
				valueS: 0,
				//valueM: [0],
				iCon: "",
				selectedcolor: "#007aff",
				modes: "default",
				selectedTextcolor: "#333",
				range: [{
					"value": 0,
					"text": "篮球"
				}, {
					"value": 1,
					"text": "足球"
				}, {
					"value": 2,
					"text": "游泳"
				}]
			}
		},
		methods: {
			fontColor() {
				const rgb = []
				for (let i = 0; i < 3; ++i) {
					let color = Math.floor(Math.random() * 256).toString(16)
					color = color.length == 1 ? '0' + color : color
					rgb.push(color)
				}
				this.selectedTextcolor = '#' + rgb.join('')
			},

			multiplesChange() {
				this.multipleChange = !this.multipleChange
				this.valueS = 0
			},
			changeColor() {
				const rgb = []
				for (let i = 0; i < 3; ++i) {
					let color = Math.floor(Math.random() * 256).toString(16)
					color = color.length == 1 ? '0' + color : color
					rgb.push(color)
				}
				this.selectedcolor = '#' + rgb.join('')
			},
			changetoList() {
				this.modes = "list"
				this.iCon = "left"
			},
			changetoButton() {
				this.modes = "button"
			},
			changetoTag() {
				this.modes = "tag"
			},
			changetoDefault() {
				this.modes = "default"
			},
			changetoIcon() {
				this.iCon = "right"
			},
			changetoICon() {
				this.iCon = "left"
			}
		},
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

	.change-mode {
		display: flex;
		flex-direction: row;
	}

	.list-view {
		display: flex;
		flex-direction: row;
	}
</style>
