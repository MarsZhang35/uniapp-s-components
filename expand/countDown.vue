<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
		<view class="container-bottom">
			<view class="title">
				概述
			</view>
			<uni-countdown :day="1" :showColon="showcolon" :splitorColor="splitorcolor" :color="fontColor" :backgroundColor="backColor"
				:show-day="showDay" :hour="2" :minute="60" :second="0"></uni-countdown>
			<uni-section title="是否显示天" type="line"></uni-section>
			<view class="show-day">
				<button class="show-day" @click="showdaies">是否显示天</button>
			</view>
			<uni-section title="随机改变颜色" type="line"></uni-section>
			<view class="change-color">
				<button class="change-color-bgc" @click="changebgc">背景颜色</button>
				<button class="change-font-color" @click="fontsColor">字体颜色</button>
				<button class="change-font-color" @click="splitorsColor">分隔符颜色</button>
			</view>
			<uni-section title="是否以冒号为分隔符" type="line"></uni-section>
			<view class="change-colon-view">
				<button class="change-colon" @click="changeColon">分隔符切换</button>
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
				cpntitle: 'CountDown 倒计时',
				cpnDescrbe: "CountDown 倒计时组件",
				cpnName: "CountDown",
				number: 5,
				showDay: true,
				backColor: "#FFFFFF",
				fontColor: "#000000",
				splitorcolor: "#000000",
				showcolon:"true"
			}
		},
		components: {
			cpninfo
		},
		methods: {
			showdaies() {
				this.showDay = !this.showDay
			},
			changebgc() {
				const rgb = []
				for (let i = 0; i < 3; ++i) {
					let color = Math.floor(Math.random() * 256).toString(16)
					color = color.length == 1 ? '0' + color : color
					rgb.push(color)
				}
				this.backColor = '#' + rgb.join('')
			},
			fontsColor() {
				const rgb = []
				for (let i = 0; i < 3; ++i) {
					let color = Math.floor(Math.random() * 256).toString(16)
					color = color.length == 1 ? '0' + color : color
					rgb.push(color)
				}
				this.fontColor = '#' + rgb.join('')
			},
			splitorsColor() {
				const rgb = []
				for (let i = 0; i < 3; ++i) {
					let color = Math.floor(Math.random() * 256).toString(16)
					color = color.length == 1 ? '0' + color : color
					rgb.push(color)
				}
				this.splitorcolor = '#' + rgb.join('')
			},
			changeColon(){
				this.showcolon = !this.showcolon
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
	
	.change-color{
		display: flex;
		flex-direction: row;
	}
</style>
