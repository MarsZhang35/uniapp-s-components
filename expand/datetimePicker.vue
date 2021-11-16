<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
		<view class="container-bottom">
			<view class="title">
				概述
			</view>
			<uni-section :title="'日期用法：' + single" type="line"></uni-section>
			<view class="example-body">
				<uni-datetime-picker :clearIcon="clearicon" :disabled="disAble" :type="typeStyle" start="2021-3-20" end="2021-11-20" />
			</view>
			<uni-section :title="'可显示现在时间：' + single" type="line"></uni-section>
			<view class="example-body">
				<uni-datetime-picker :clearIcon="clearicon" :disabled="disAble" returnType="timestamp" start="2021-3-20" end="2021-11-20" />
			</view>
			<uni-section :title="'日期+时间：' + datetimesingle" type="line"></uni-section>
			<view class="example-body">
				<uni-datetime-picker :clearIcon="clearicon" :disabled="disAble" type="datetime" v-model="datetimesingle" @change="changeLog" />
			</view>
			<uni-section :title="'日期范围用法：' + '[' + range + ']'" type="line"></uni-section>
			<view class="example-body">
				<uni-datetime-picker :clearIcon="clearicon" :disabled="disAble" v-model="range" type="daterange" start="2021-3-20" end="2021-5-20"
					rangeSeparator="至" />
			</view>
			<uni-section title="是否可以更改" type="line"></uni-section>
			<view class="change-disable">
				<button class="change-disable" @click="changeDisable">只读/改写</button>
			</view>
			<uni-section title="是否显示清除按钮" type="line"></uni-section>
			<view class="clear-icon">
				<button class="clear-icon" @click="appearIcon">显示/隐藏</button>
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
				cpntitle: 'uni-datetime-picker 日期选择器',
				cpnDescrbe: "uni-datetime-picker 日期时间选择器，支持日历，支持范围选择",
				cpnName: "uni-caluni-datetime-pickerendar",
				number: 35.4,
				single: "2021-10-27",
				datetimesingle: "2021-10-27",
				range: ["2021-10-8", "2021-11-20"],
				disAble:false,
				clearicon:true
			}
		},
		components: {
			cpninfo
		},
		methods: {
			changeDisable(){
				this.disAble = !this.disAble
			},
			appearIcon(){
				this.clearicon = !this.clearicon
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
</style>
