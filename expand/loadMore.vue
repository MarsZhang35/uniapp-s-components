<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
		<view class="container-bottom-view">
			<view class="title">
				概述
			</view>
			<uni-load-more :color="color" iconType="auto" :status="status" :contentText="contentText"></uni-load-more>
			<uni-load-more :color="color" iconType="circle" :status="status" :contentText="contentText"></uni-load-more>
			<uni-load-more iconSize="36" :color="color" iconType="snow" :status="status" :contentText="contentText"></uni-load-more>
			<uni-section title="不同状态" type="line"></uni-section>
			<view class="status-view">
				<button class="status" @click="statusm">查看更多</button>
				<button class="status" @click="statusl">加载中</button>
				<button class="status" @click="statuslm">没有更多</button>
			</view>
			<uni-section title="改变颜色" type="line"></uni-section>
			<view class="change-color">
				<button class="change-color" @click="changeColor">改变颜色</button>
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
				contentText: {
					cpntitle: 'uni-load-more 加载更多',
					cpnDescrbe: "LoadMore 组件，常用在列表里面，做滚动加载使用。",
					cpnName: "uni-load-more",
					number: 10.8,
					contentdown: '查看更多',
					contentrefresh: '加载中',
					contentnomore: '没有更多'
				},
				status:"more",
				color:"#777777"

			}
		},
		components: {
			cpninfo
		},
		methods: {
			statusm(){
				this.status = "more"
			},
			statusl(){
				this.status = "loading"
			},
			statuslm(){
				this.status = "nomore"
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
	
	.status-view{
		display: flex;
		flex-direction: row;
	}
</style>
