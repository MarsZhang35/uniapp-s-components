<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
		<view class="container-bottom">
			<view class="title">
				概述
			</view>
			<button @click="showDrawer">点这里弹出</button>
			<uni-drawer ref="showRight" :mode="modes" :mask-click="maskClick">
				<scroll-view style="height: 100%;" scroll-y="true">
					<button @click="closeDrawer" >关闭</button>
					<view v-for="item in 60" :key="item">可滚动内容 {{ item }}</view>
				</scroll-view>
			</uni-drawer>
			<uni-section title="是否点击外侧可以关闭抽屉" type="line"></uni-section>
			<view class="mask-click">
				<button class="mask-click" @click="masksClick">可以/不可以</button>
			</view>
			<uni-section title="从哪一侧滑出(mode不能动态生成)" type="line"></uni-section>
			<view class="modes-view">
				<button class="modes-right" @click="modesRight">右侧</button>
				<button class="modes-left" @click="modesLeft">左侧</button>
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
				cpntitle: 'uni-drawer 抽屉',
				cpnDescrbe: "抽屉式导航，用于展示侧滑菜单，侧滑导航。通过数据驱动的单选框和复选框",
				cpnName: "uni-drawer",
				number: 4.9,
				maskClick:false,
				modes:"left"
			}
		},
		components: {
			cpninfo
		},
		methods: {
			showDrawer() {
				this.$refs.showRight.open();
			},
			closeDrawer() {
				this.$refs.showRight.close();
			},
			masksClick(){
				this.maskClick = !this.maskClick
			},
			modesRight(){
				this.modes = "right"
			},
			modesLeft(){
				this.modes = "left"
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
	
	.modes-view{
		display: flex;
		flex-direction: row;
	}
</style>
