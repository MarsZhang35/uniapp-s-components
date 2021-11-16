<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
		<view class="container-bottom-view">
			<view class="title">
				概述
			</view>
			<view class=" swipe-view">
				<uni-swipe-action>
					<!-- 基础用法 -->
					<uni-swipe-action-item :right-options="options" :left-options="options">
						<view class="swipe-font">SwipeAction 使用场景</view>
					</uni-swipe-action-item>
				</uni-swipe-action>
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
				cpntitle: 'uni-swipe-action 滑动操作',
				cpnDescrbe: "SwipeAction 滑动操作操作组件",
				cpnName: "uni-swipe-action",
				number: 20.3,
				options: [{
					text: '取消',
					style: {
						backgroundColor: '#007aff'
					}
				}, {
					text: '确认',
					style: {
						backgroundColor: '#dd524d'
					}
				}]
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

	.swipe-view {
		background-color: #eaedf8;
		display: flex;
		flex-direction: column;
		margin: 10rpx 0;
	}

	.swipe-font {
		display: flex;
		justify-content: center;
		height: 70rpx;
		line-height: 70rpx;
	}
</style>
