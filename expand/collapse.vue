<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
		<view class="container-bottom">
			<view class="title">
				概述
			</view>
			<uni-collapse>
				<uni-collapse-item class="first-collapse" :show-arrow="showArrow" title="默认开启"
					:show-animation="showAnimation" :open="true" thumb="/static/c2.png">
					<text class="first-collapse-font"> 显示内容1</text>
				</uni-collapse-item>
				<uni-collapse-item title="禁用状态" disabled :show-arrow="showArrow">
				</uni-collapse-item>
			</uni-collapse>
			<uni-section title="是否有动画" type="line"></uni-section>
			<view class="">
				<button class="show-animation" @click="showAnimations">是否显示动画</button>
			</view>
			<uni-section title="是否有箭头" type="line"></uni-section>
			<view class="">
				<button class="show-arrow" @click="showArrows">是否显示箭头</button>
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
				cpntitle: 'uni-collapse 折叠面板',
				cpnDescrbe: "Collapse 组件，可以折叠 / 展开的内容区域。",
				cpnName: "uni-collapse",
				number: 9.6,
				showAnimation: true,
				showArrow: true
			}
		},
		components: {
			cpninfo
		},
		methods: {
			showAnimations() {
				this.showAnimation = !this.showAnimation
			},
			showArrows() {
				this.showArrow = !this.showArrow
			}
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

	.first-collapse-font {
		display: flex;
		justify-content: center;
	}
</style>
