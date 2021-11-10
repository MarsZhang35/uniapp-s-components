<template>
	<view class="container">
		<view class="container-top">
			<view class="title">
				uni-badge 数字角标
			</view>
			<view class="description">
				view数字角标（徽章）组件，在元素周围展示消息提醒，一般用于列表、九宫格、按钮等地方。
			</view>
			<view class="author">
				<view class="author-detail">
					作者： DCloud前端团队 已实名认证
				</view>
				<image class="logo-image" src="/static/logo.png"></image>
			</view>
			插件ID：uni-badge <br>
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
			<view class="box-container">
				<uni-badge :inverted="isBgc" :is-dot="isDot" :size='badgeSize' :text="maxNum" :max-num="maxNum-1"
					:offset="offSet" :absolute='items[current].location' :type="typeColor">
					<view class="box"></view>
				</uni-badge>
			</view>
			<uni-section title="偏移量" type="line"></uni-section>
			<view class="change-postion-view">
				<button class="change-postin-away" @click="changePostionAway">远离</button>
				<button class="change-postin-back" @click="changePostionBack">返回</button>
			</view>
			<uni-section title="展示封顶的数字值" type="line"></uni-section>
			<view class="change-max-num-view">
				<input class="inputNum" @input="inputData" type="number" placeholder="请输入想显示的最大数值" v-model="maxNum"
					focus />
			</view>
			<uni-section title="改变底色" type="line"></uni-section>
			<view class="change-color">
				<button class="change-color-blue" @click="changetoBlue">蓝色</button>
				<button class="change-color-green" @click="changetoGreen">绿色</button>
				<button class="change-color-yellow" @click="changetoYellow">黄色</button>
				<button class="change-color-red" @click="changetoRed">红色</button>
				<button class="change-color-default" @click="changetoDefault">灰色</button>
			</view>
			<view class="box-container">
				<uni-badge :inverted="isBgc" :is-dot="isDot" :size='badgeSize' :text="maxNum" :max-num="maxNum-1"
					:offset="offSet" :absolute='items[current].location' :type="typeColor">
					<view class="box"></view>
				</uni-badge>
			</view>
			<uni-section title="改变大小" type="line"></uni-section>
			<view class="change-size">
				<button class="change-sizer-small" @click="changetoSmall">变小</button>
				<button class="change-sizer-normal" @click="changetoNormal">变中</button>
			</view>
			<uni-section title="改变方位" type="line"></uni-section>
			<view class="change-location">
				<radio-group @change="radioChange">
					<label class="change-location-view" v-for="(item, index) in items" :key="item.location">
						<view>
							<radio :value="item.location" :checked="index === current" @click='choiceLocation(index)' />
						</view>
						<view>{{item.name}}</view>
					</label>
				</radio-group>
			</view>
			<uni-section title="仅显示点" type="line"></uni-section>
			<view class="change-style">
				<button class="change-sizer-point" @click="changetoPoint">显示点</button>
				<button class="change-sizer-num" @click="changetoNum">显示数字</button>
			</view>
			<uni-section title="有无背景" type="line"></uni-section>
			<view class="change-style">
				<button class="change-bgc" @click="changetoBgc">有无背景</button>
			</view>

		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				badgeSize: "noraml",
				typeColor: "default",
				isDot: false,
				isBgc: false,
				maxNum: "100",
				offSet:[0,0],
				items: [{
						location: "rightTop",
						name: "右上"
					},
					{
						location: "rightBottom",
						name: "右下"
					},
					{
						location: "leftBottom",
						name: "左下"
					},
					{
						location: "leftTop",
						name: "左上"
					},
				],
				current: 0,
			}
		},
		methods: {
			changePostionAway(){
				this.offSet=[-10,-10]
			},
			changePostionBack(){
				this.offSet=[0,0]
			},
			changetoBlue() {
				this.typeColor = "primary"
			},
			changetoGreen() {
				this.typeColor = "success"
			},
			changetoYellow() {
				this.typeColor = "warning"
			},
			changetoRed() {
				this.typeColor = "error"
			},
			changetoDefault() {
				this.typeColor = "default"
			},
			changetoSmall() {
				this.badgeSize = "small"
			},
			changetoNormal() {
				this.badgeSize = "normal"
			},
			radioChange: function(evt) {
				for (let i = 0; i < this.items.length; i++) {
					if (this.items[i].location === evt.detail.location) {
						this.current = i;
						break;
					}
				}
			},
			choiceLocation(current) {
				this.current = current
			},
			changetoPoint() {
				this.isDot = true
			},
			changetoNum() {
				this.isDot = false
			},
			changetoBgc() {
				this.isBgc = !this.isBgc
			},
			inputData(e) {
				this.maxNum = e.detail.value
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
		width: 85%;
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

	/* 	之前的可复用 */
	.box-container {
		padding: 30rpx;
		display: flex;
		justify-content: center;
	}

	.box {
		width: 100rpx;
		height: 100rpx;
		background-color: #dce1e6;
	}
	
	.change-postion-view{
		display: flex;
		flex-direction: row;
	}
	.change-color {
		display: flex;
		flex-direction: row;
	}

	.change-color-blue {
		background-color: blue;
	}

	.change-color-green {
		background-color: green;
	}

	.change-color-yellow {
		background-color: yellow;
	}

	.change-color-red {
		background-color: red;
	}

	.change-color-default {
		background-color: grey;
	}

	.change-size {
		display: flex;
		flex-direction: row;
	}

	.change-location {}

	.change-location-view {
		display: flex;
		flex-direction: row;
	}

	.change-style {
		display: flex;
		flex-direction: row;
	}

	.inputNum {
		border: 1px black solid;
	}
</style>

