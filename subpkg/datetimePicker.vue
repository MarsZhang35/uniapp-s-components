<template>
	<view class="container">
		<view class="container-top">
			<view class="title">
				uni-datetime-picker 日期选择器
			</view>
			<view class="description">
				uni-datetime-picker 日期时间选择器，支持日历，支持范围选择
			</view>
			<view class="author">
				<view class="author-detail">
					作者： DCloud前端团队
				</view>
				<image class="logo-image" src="/static/logo.png"></image>
			</view>
			插件ID：uni-datetime-picker <br>
			插件包体积：35.4KB
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
			<uni-section :title="'日期用法：' + single" type="line"></uni-section>
			<view class="example-body">
				<uni-datetime-picker :clearIcon="clearicon" :disabled="disAble" :type="typeStyle" start="2021-3-20" end="2021-11-20" />
			</view>
			<uni-section :title="'可显示现在时间：' + single" type="line"></uni-section>
			<view class="example-body">
				<uni-datetime-picker :clearIcon="clearicon" :disabled="disAble" returnType="timestamp" start="2021-3-20" end="2021-11-20" />
			</view>
			<uni-section :title="'日期+时间：' + datetimesingle" type="line"></uni-section>
			<view class="example-body">
				<uni-datetime-picker :clearIcon="clearicon" :disabled="disAble" type="datetime" v-model="datetimesingle" @change="changeLog" />
			</view>
			<uni-section :title="'日期范围用法：' + '[' + range + ']'" type="line"></uni-section>
			<view class="example-body">
				<uni-datetime-picker :clearIcon="clearicon" :disabled="disAble" v-model="range" type="daterange" start="2021-3-20" end="2021-5-20"
					rangeSeparator="至" />
			</view>
			<uni-section title="是否可以更改" type="line"></uni-section>
			<view class="change-disable">
				<button class="change-disable" @click="changeDisable">只读/改写</button>
			</view>
			<uni-section title="是否显示清除按钮" type="line"></uni-section>
			<view class="clear-icon">
				<button class="clear-icon" @click="appearIcon">显示/隐藏</button>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				single: "2021-10-27",
				datetimesingle: "2021-10-27",
				range: ["2021-10-8", "2021-11-20"],
				disAble:false,
				clearicon:true
			}
		},
		methods: {
			changeDisable(){
				this.disAble = !this.disAble
			},
			appearIcon(){
				this.clearicon = !this.clearicon
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
