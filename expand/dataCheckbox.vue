<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
		<view class="container-bottom">
			<view class="title">
				概述
			</view>
			<uni-data-checkbox :selectedTextColor="selectedTextcolor" :icon="iCon" :mode="modes"
				:selectedColor="selectedcolor" :multiple="multipleChange" v-model="valueS" :localdata="range">
			</uni-data-checkbox>
			<uni-section title="改变字体颜色" type="line"></uni-section>
			<view class="font-color">
				<button class="font-color" @click="fontColor">换字体颜色</button>
			</view>
			<uni-section title="切换单/多选" type="line"></uni-section>
			<view class="multipleChange-view">
				<button class="multipleChange" @click="multiplesChange">切换单/多选</button>
			</view>
			<uni-data-checkbox :selectedTextColor="selectedTextcolor" :icon="iCon" :mode="modes"
				:selectedColor="selectedcolor" :multiple="multipleChange" v-model="valueS" :localdata="range">
			</uni-data-checkbox>
			<uni-section title="改变mode" type="line"></uni-section>
			<view class="change-mode">
				<button class="change-button" @click="changetoButton">Button模式</button>
				<button class="change-tag" @click="changetoTag">Tag模式</button>
				<button class="change-default" @click="changetoDefault">Default模式</button>
			</view>
			<uni-section title="List模式下" type="line"></uni-section>
			<view class="list-view">
				<button class="change-mode" @click="changetoList">List模式</button>
				<button class="change-icon" @click="changetoIcon"> icon显示右边</button>
				<button class="change-icon" @click="changetoICon"> icon显示左边</button>
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
				cpntitle: 'uni-data-checkbox 数据选择器',
				cpnDescrbe: "通过数据驱动的单选框和复选框",
				cpnName: "uni-data-checkbox",
				number: 9.5,
				multipleChange: false,
				valueS: 0,
				//valueM: [0],
				iCon: "",
				selectedcolor: "#007aff",
				modes: "default",
				selectedTextcolor: "#333",
				range: [{
					"value": 0,
					"text": "篮球"
				}, {
					"value": 1,
					"text": "足球"
				}, {
					"value": 2,
					"text": "游泳"
				}]
			}
		},
		components: {
			cpninfo
		},
		methods: {
			fontColor() {
				const rgb = []
				for (let i = 0; i < 3; ++i) {
					let color = Math.floor(Math.random() * 256).toString(16)
					color = color.length == 1 ? '0' + color : color
					rgb.push(color)
				}
				this.selectedTextcolor = '#' + rgb.join('')
			},

			multiplesChange() {
				this.multipleChange = !this.multipleChange
				this.valueS = 0
			},
			changeColor() {
				const rgb = []
				for (let i = 0; i < 3; ++i) {
					let color = Math.floor(Math.random() * 256).toString(16)
					color = color.length == 1 ? '0' + color : color
					rgb.push(color)
				}
				this.selectedcolor = '#' + rgb.join('')
			},
			changetoList() {
				this.modes = "list"
				this.iCon = "left"
			},
			changetoButton() {
				this.modes = "button"
			},
			changetoTag() {
				this.modes = "tag"
			},
			changetoDefault() {
				this.modes = "default"
			},
			changetoIcon() {
				this.iCon = "right"
			},
			changetoICon() {
				this.iCon = "left"
			}
		},
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

	.change-mode {
		display: flex;
		flex-direction: row;
	}

	.list-view {
		display: flex;
		flex-direction: row;
	}
</style>
