<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
		<view class="container-bottom">
			<view class="title">
				概述
			</view>
			<uni-data-picker step-searh="false" :clearIcon="clearicon" :readonly="readOnly" :localdata="items" popup-title="请选择班级">
			</uni-data-picker>
			<uni-section title="是否为只读" type="line"></uni-section>
			<view class="ready-only">
				<button class="ready-only" @click="changetoRead">切换</button>
			</view>
			<uni-section title="是否显示清除按钮" type="line"></uni-section>
			<view class="appear-icon">
				<button class="appear-icon" @click="appearIcon">切换</button>
			</view>
			<uni-section title="分步查询时，点击节点请求数据" type="line"></uni-section>
			<view class="step-searh">
				<button class="step-searh" @click="stepsSearh">切换</button>
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
				cpntitle: 'uni-data-picker 数据驱动的picker选择器',
				cpnDescrbe: "单列、多列级联选择器，常用于省市区城市选择、公司部门选择、多级分类等场景",
				cpnName: "uni-data-picker",
				number: 15.4,
				readOnly:false,
				clearicon:true,
				stepSearh:true,
				items: [{
						text: "一年级",
						value: "1-0",
						children: [{
								text: "1.1班",
								value: "1-1"
							},
							{
								text: "1.2班",
								value: "1-2"
							}
						]
					},
					{
						text: "二年级",
						value: "2-0",
						children: [{
								text: "2.1班",
								value: "2-1"
							},
							{
								text: "2.2班",
								value: "2-2"
							}
						]
					},
					{
						text: "三年级",
						value: "3-0"
					}
				]
			}
		},
		components: {
			cpninfo
		},
		methods: {
			changetoRead(){
				this.readOnly = !this.readOnly
			},
			appearIcon(){
				this.clearicon = !this.clearicon
			},
			stepsSearh(){
				this.stepSearh = !this.stepSearh
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
