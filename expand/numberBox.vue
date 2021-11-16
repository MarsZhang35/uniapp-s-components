<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
		<view class="container-bottom-view">
			<view class="title">
				概述
			</view>
			<uni-section title="基本引用" type="line"></uni-section>
			<uni-number-box />
			<uni-section title="最小是2 最大是7 初始值是4" type="line"></uni-section>
			<uni-number-box :min="2" :max="7" :value="4" />
			<uni-section title="每次增常和减少0.1" type="line"></uni-section>
			<uni-number-box :step="0.1" />
			<uni-section title="不可更改" type="line"></uni-section>
			<uni-number-box :disabled="true" />
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
				cpntitle: 'uni-number-box 数字输入框',
				cpnDescrbe: "NumberBox 带加减按钮的数字输入框组件，用户可以控制每次点击增加的数值，支持小数。",
				cpnName: "uni-number-box",
				number: 4.6,
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
