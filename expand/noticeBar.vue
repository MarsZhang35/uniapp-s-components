<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
		<view class="container-bottom-view">
			<view class="title">
				概述
			</view>
			<!-- 基本用法 -->
			<uni-notice-bar :color="color" :backgroundColor="backgroundcolor" single="true" text="[单行] 这是 NoticeBar 通告栏，这是 NoticeBar 通告栏，这是 NoticeBar 通告栏">
			</uni-notice-bar>
			<uni-notice-bar :color="color" :backgroundColor="backgroundcolor" text="[多行] 这是 NoticeBar 通告栏，这是 NoticeBar 通告栏，这是 NoticeBar 通告栏，这是 NoticeBar 通告栏">
			</uni-notice-bar>

			<!-- 文字滚动 -->
			<uni-notice-bar :color="color" :backgroundColor="backgroundcolor" scrollable="true" single="true"
				text="[单行] 这是 NoticeBar 通告栏，这是 NoticeBar 通告栏，这是 NoticeBar 通告栏"></uni-notice-bar>

			<!-- 显示图标 -->
			<uni-notice-bar :color="color" :backgroundColor="backgroundcolor" showIcon="true"
				text="[多行] 这是 NoticeBar 通告栏，这是 NoticeBar 通告栏，这是 NoticeBar 通告栏这是 NoticeBar 通告栏，这是 NoticeBar 通告栏，这是 NoticeBar 通告栏">
			</uni-notice-bar>

			<!-- 显示关闭按钮 -->
			<uni-notice-bar :color="color" :backgroundColor="backgroundcolor" showClose="true" showIcon="true" text="这是 NoticeBar 通告栏，这是 NoticeBar 通告栏，这是 NoticeBar 通告栏">
			</uni-notice-bar>

			<!-- 查看更多 -->
			<uni-notice-bar :color="color" :backgroundColor="backgroundcolor" @getmore="getMore" :showGetMore="true" moreText="查看更多" single="true"
				text="[单行] 这是 NoticeBar 通告栏，这是 NoticeBar 通告栏，这是 NoticeBar 通告栏"></uni-notice-bar>
			<uni-section title="改变颜色" type="line"></uni-section>
			<view class="change-color-view">
				<button class="change-color" @click="changeBgc">背景颜色</button>
				<button class="change-color" @click="changeColor">文字颜色</button>
			</view>
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
				cpntitle: 'uni-notice-bar 通告栏',
				cpnDescrbe: "NoticeBar 通告栏组件，常用于展示公告信息，可设为滚动公告",
				cpnName: "uni-notice-bar",
				number: 5.5,
				backgroundcolor:"#fffbe8",
				color:"#de8c17"
			}
		},
		components: {
			cpninfo
		},
		methods: {
			getMore() {
				uni.showToast({
					title: '点击查看更多',
					icon: 'none'
				});
			},
			changeBgc(){
				const rgb = []
				for (let i = 0; i < 3; ++i) {
					let color = Math.floor(Math.random() * 256).toString(16)
					color = color.length == 1 ? '0' + color : color
					rgb.push(color)
				}
				this.backgroundcolor = '#' + rgb.join('')
			},
			changeColor(){
				const rgb = []
				for (let i = 0; i < 3; ++i) {
					let color = Math.floor(Math.random() * 256).toString(16)
					color = color.length == 1 ? '0' + color : color
					rgb.push(color)
				}
				this.color = '#' + rgb.join('')
			}
		}
	}
</script>

<style>
	.container {
		padding-bottom: 150rpx;
	}

	.title{
		width: 100%;
		font-size: 50rpx;
		font-weight: bold;
		background-color: #6fdbdd;
		display: flex;
		justify-content: center;
		align-items: flex-start;
	}
	
	.change-color-view{
		display: flex;
		flex-direction: row;
	}
</style>
