<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
		<view class="container-bottom-view">
			<view class="title">
				概述
			</view>
			<uni-section title="正常显示" type="line"></uni-section>
			<uni-rate v-model="value" />

			<uni-section title="不支持滑动手势选择评分" type="line"></uni-section>
			<uni-rate :touchable="false" :value="5" />

			<uni-section title="设置尺寸大小" type="line"></uni-section>
			<uni-rate :size="18" :value="5" />

			<uni-section title="设置评分数" type="line"></uni-section>
			<uni-rate :max="10" :value="5" />

			<uni-section title="设置星星间隔" type="line"></uni-section>
			<uni-rate :value="4" :margin="20" />

			<uni-section title="设置颜色" type="line"></uni-section>
			<uni-rate :value="3" color="#bbb" active-color="red" />

			<uni-section title="选择半星" type="line"></uni-section>
			<uni-rate allow-half :value="3.5" />

			<uni-section title="只读状态" type="line"></uni-section>
			<uni-rate :readonly="true" :value="2" />

			<uni-section title="禁用状态" type="line"></uni-section>
			<uni-rate :disabled="true" disabledColor="#ccc" :value="3" />

			<uni-section title="未选中的星星为镂空状态" type="line"></uni-section>
			<uni-rate :value="3" :is-fill="false" />
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
				cpntitle: 'uni-rate 评分',
				cpnDescrbe: "Rate 评分组件，可自定义评分星星图标的大小、间隔、评分数。",
				cpnName: "uni-rate",
				number: 6.2,
				value: 1
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
