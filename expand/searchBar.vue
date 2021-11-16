<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
		<view class="container-bottom-view">
			<view class="title">
				概述
			</view>
			<!-- 基本用法 -->
			<uni-search-bar :bgColor="bgColor" @confirm="search" placeholder="请输入搜索内容"></uni-search-bar>

			<!-- v-model 用法 -->
			<uni-search-bar :bgColor="bgColor" placeholder="请输入搜索内容" @confirm="search" :focus="true" v-model="searchValue"
				@cancel="cancel" @clear="clear"></uni-search-bar>
			<view class="">
				当前输入为：{{searchValue}}
			</view>
			<!-- 设置圆角 -->
			<uni-search-bar :bgColor="bgColor" placeholder="自定义图标" :radius="100" @confirm="search">
				<uni-icons slot="searchIcon" color="#999999" size="18" type="home" />
			</uni-search-bar>
			<uni-section title="背景色" type="line"></uni-section>
			<view class="change-bgc">
				<button class="change-bgc" @click="changeBgc">改变背景颜色</button>
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
				cpntitle: 'uni-search-bar 搜索栏',
				cpnDescrbe: "搜索栏组件，通常用于搜索商品、文章等",
				cpnName: "uni-search-bar",
				number: 6,
				searchValue: '123123',
				bgColor:"#F8F8F8"
			}
		},
		components: {
			cpninfo
		},
		methods: {
			search(res) {
				uni.showToast({
					title: '搜索：' + res.value,
					icon: 'none'
				})
			},
			clear(res) {
				uni.showToast({
					title: 'clear事件，输入值为：' + res.value,
					icon: 'none'
				})
			},
			cancel(res) {
				uni.showToast({
					title: '点击取消，输入值为：' + res.value,
					icon: 'none'
				})
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
</style>
