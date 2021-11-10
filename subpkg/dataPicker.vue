<template>
	<view class="container">
		<view class="container-top">
			<view class="title">
				uni-data-picker 数据驱动的picker选择器
			</view>
			<view class="description">
				单列、多列级联选择器，常用于省市区城市选择、公司部门选择、多级分类等场景
			</view>
			<view class="author">
				<view class="author-detail">
					作者： DCloud前端团队
				</view>
				<image class="logo-image" src="/static/logo.png"></image>
			</view>
			插件ID：uni-data-picker <br>
			插件包体积：15.4KB
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
			<uni-data-picker step-searh="false" :clearIcon="clearicon" :readonly="readOnly" :localdata="items" popup-title="请选择班级">
			</uni-data-picker>
			<uni-section title="是否为只读" type="line"></uni-section>
			<view class="ready-only">
				<button class="ready-only" @click="changetoRead">切换</button>
			</view>
			<uni-section title="是否显示清除按钮" type="line"></uni-section>
			<view class="appear-icon">
				<button class="appear-icon" @click="appearIcon">切换</button>
			</view>
			<uni-section title="分步查询时，点击节点请求数据" type="line"></uni-section>
			<view class="step-searh">
				<button class="step-searh" @click="stepsSearh">切换</button>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				readOnly:false,
				clearicon:true,
				stepSearh:true,
				items: [{
						text: "一年级",
						value: "1-0",
						children: [{
								text: "1.1班",
								value: "1-1"
							},
							{
								text: "1.2班",
								value: "1-2"
							}
						]
					},
					{
						text: "二年级",
						value: "2-0",
						children: [{
								text: "2.1班",
								value: "2-1"
							},
							{
								text: "2.2班",
								value: "2-2"
							}
						]
					},
					{
						text: "三年级",
						value: "3-0"
					}
				]
			}
		},
		methods: {
			changetoRead(){
				this.readOnly = !this.readOnly
			},
			appearIcon(){
				this.clearicon = !this.clearicon
			},
			stepsSearh(){
				this.stepSearh = !this.stepSearh
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
