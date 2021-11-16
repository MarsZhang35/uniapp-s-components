<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
		<view class="container-bottom-view">
			<view class="title">
				概述
			</view>
			<uni-group title="分组1 普通模式" top="20">
			    <view>分组1 的内容</view>
			    <view>分组1 的内容</view>
			</uni-group>
			
			<uni-group title="分组2 card模式" top="20" mode="card">
			    <view>分组2 的内容</view>
			    <view>分组2 的内容</view>
			</uni-group>
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
				cpntitle: 'uni-group 分组',
				cpnDescrbe: "分组组件可用于将组件用于分组，添加间隔，以产生明显的区块",
				cpnName: "uni-group",
				number: 3.4,
			}
		},
		components: {
			cpninfo
		},
		methods: {
			
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
