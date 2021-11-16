<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
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
	import {
		cpninfo,
		cpntitle,
		cpnDescrbe,
		cpnName,
		number
	} from '../component/cpninfo.vue'
	export default {
		data() {
			return {
				iShadow: false,
				modeStyle: "basic",
				moreInfo: "这里有更多信息",
				cpntitle: 'uni-card 卡片',
				cpnDescrbe: "Card 组件，提供常见的卡片样式。",
				cpnName: "uni-card",
				number: 5.5,
			}
		},
		components: {
			cpninfo
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
