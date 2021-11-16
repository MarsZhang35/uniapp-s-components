<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
		<view class="container-bottom-view">
			<view class="title">
				概述
			</view>
			<uni-swiper-dot :dotsStyles="dotsStyles" :border="border" :info="info" :current="current" field="content"
				:mode="mode">
				<swiper class="swiper-box" @change="change">
					<swiper-item v-for="(item ,index) in info" :key="index">
						<view class="swiper-item">
							{{item.content}}
						</view>
					</swiper-item>
				</swiper>
			</uni-swiper-dot>
			<uni-section title="模式选择" type="line"></uni-section>
			<view class="change-mode-view">
				<button class="change-mode" @click="changetoDefault">default</button>
				<button class="change-mode" @click="changesDot">dot</button>
				<button class="change-mode" @click="changetoRound">round</button>
				<button class="change-mode" @click="changesNav">nav</button>
				<button class="change-mode" @click="changesIndexes">indexes</button>
			</view>
			<uni-section title="改颜色" type="line"></uni-section>
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
				cpntitle: 'uni-swiper-dot 轮播图指示点',
				cpnDescrbe: "自定义轮播图指示点组件",
				cpnName: "uni-swiper-dot",
				number: 5,
				info: [{
					content: '内容 A'
				}, {
					content: '内容 B'
				}, {
					content: '内容 C'
				}],
				current: 0,
				mode: 'default',
				dotsStyles: {
					backgroundColor: 'rgba(0, 0, 0, .3)',
					border: '1px rgba(0, 0, 0, .3) solid',
					color: '#333',
					selectedBackgroundColor: 'rgba(0, 0, 0, .3)',
					selectedBorder: '1px rgba(0, 0, 0, .9) solid'
				}
			}
		},
		components: {
			cpninfo
		},
		methods: {
			change(e) {
				this.current = e.detail.current;
			},
			changetoDefault() {
				this.mode = 'default'
			},
			changesDot() {
				this.mode = 'dot'
			},
			changesNav() {
				this.mode = 'nav'
			},
			changesIndexes() {
				this.mode = 'indexes'
			},
			changetoRound() {
				this.mode = 'round'
			},
			changeColor(){
				const rgb = []
				for (let i = 0; i < 3; ++i) {
					let color = Math.floor(Math.random() * 256).toString(16)
					color = color.length == 1 ? '0' + color : color
					rgb.push(color)
				}
				this.dotsStyles.backgroundColor = '#' + rgb.join('')
				this.dotsStyles.border = '#' + rgb.join('')
				this.dotsStyles.selectedBackgroundColor = '#' + rgb.join('')
				this.dotsStyles.selectedBorder = '#' + rgb.join('')
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

	.change-mode-view {
		display: flex;
		flex-direction: row;
	}
</style>
