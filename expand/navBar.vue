<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
		<view class="container-bottom-view">
			<view class="title">
				概述
			</view>
			<uni-section title="左右都有文字" type="line"></uni-section>
			<uni-nav-bar @clickLeft="back" @clickTitle="clickTitle" @clickRight="showMenu" left-icon="back"
				left-text="返回" right-text="菜单" title="导航栏组件"></uni-nav-bar>
			<uni-section title="可扫码" type="line"></uni-section>
			<uni-nav-bar color="#333333" background-color="white" right-icon="scan" @clickLeft="showCity"
				@clickRight="scan">
				<block slot="left">
					<view class="city">
						<view><text style="font-size: 14px">北京</text></view>
						<uni-icons type="arrowdown" color="#333333" size="22" />
					</view>
				</block>
				<view class="input-view">
					<uni-icons style="line-height: 30px;" type="search" size="22" color="#666666" />
					<input confirm-type="search" class="nav-bar-input" type="text" placeholder="输入搜索关键词"
						@confirm="confirm">
				</view>
			</uni-nav-bar>
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
				cpntitle: 'uni-nav-bar 自定义导航栏',
				cpnDescrbe: "自定义导航栏组件，主要用于头部导航。",
				cpnName: "uni-nav-bar",
				number:4.8,
			}
		},
		components: {
			cpninfo
		},
		methods: {
			back() {
				uni.navigateBack({
					url: '/pages/index/index'
				})
			},
			clickTitle() {
				uni.showToast({
					title: "这是中间"
				})
			},
			showMenu() {
				uni.showToast({
					title: "这是菜单"
				})
			},
			showCity() {
				uni.showToast({
					title: '选择城市'
				})
			},
			scan() {
				uni.showToast({
					title: '扫码'
				})
			},
			confirm() {
				uni.showToast({
					title: '搜索'
				})
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

	.city {
		display: flex;
		flex-direction: row;
		align-items: center;
	}

	.input-view {
		display: flex;
		flex-direction: row;
		flex: 1;
		background-color: #f8f8f8;
		height: 60rpx;
		border-radius: 30rpx;
		padding: 0 30rpx;
		flex-wrap: nowrap;
		line-height: 60rpx;
	}

	.nav-bar-input {
		height: 60rpx;
		line-height: 60rpx;
		padding: 0 10rpx;
		font-size: 28rpx;
		background-color: #f8f8f8;
	}
</style>
