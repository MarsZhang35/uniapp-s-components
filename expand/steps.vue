<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
		<view class="container-bottom-view">
			<view class="title">
				概述
			</view>
			<uni-steps
				:options="[{title: '事件一',desc:'2018-11-11'}, {title: '事件二',desc:'2018-11-12'}, {title: '事件三',desc:'2018-11-13'}, {title: '事件四',desc:'2018-11-14'}]"
				:activeColor="activeColor" :direction="direction" :active="active">
			</uni-steps>
			<uni-section title="改变状态" type="line"></uni-section>
			<view class="change-style-view">
				<button class="change-style" @click="changeActive">改变状态</button>
			</view>
			<uni-section title="排列顺序" type="line"></uni-section>
			<view class="change-direction-view">
				<button class="change-direction" @click="changeDirection">改变排列</button>
			</view>
			<uni-section title="背景色" type="line"></uni-section>
			<view class="change-bgc">
				<button class="change-bgc" @click="changeBgc">改变颜色</button>
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
				cpntitle: 'uni-steps 步骤条',
				cpnDescrbe: "步骤条组件，提供横向和纵向两种布局格式。",
				cpnName: "uni-steps",
				number: 3.8,
				active: "0",
				direction: "row",
				activeColor:"#1aad19"
			}
		},
		components: {
			cpninfo
		},
		methods: {
			changeActive() {
				if (this.active < 4) {
					this.active++
				} 
				if(this.active === 4) {
					this.active = 0
				}
			},
			changeDirection() {
				if (this.direction === "column") {
					this.direction = "row"
				} else {
					this.direction = "column"
				}
			},
			changeBgc() {
				const rgb = []
				for (let i = 0; i < 3; ++i) {
					let color = Math.floor(Math.random() * 256).toString(16)
					color = color.length == 1 ? '0' + color : color
					rgb.push(color)
				}
				this.activeColor = '#' + rgb.join('')
			},
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
