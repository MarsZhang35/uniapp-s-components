<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
		<view class="container-bottom">
			<view class="title">
				概述
			</view>
			<uni-combox label="所在城市" :candidates="cities" placeholder="请选择所在城市" emptyTips="啥都没有"></uni-combox>
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
				cpntitle: 'uni-combox 组合框',
				cpnDescrbe: "可以选择也可以输入的表单项",
				cpnName: "uni-combox",
				number: 4,
				cities: ['上海', '北京', '广州', '深圳']
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
