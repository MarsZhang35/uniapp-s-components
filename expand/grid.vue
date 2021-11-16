<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
		<view class="container-bottom-view">
			<view class="title">
				概述
			</view>
			<uni-grid :column="column" :showBorder="showBorder">
				<uni-grid-item>
					<text class="text">文本</text>
				</uni-grid-item>
				<uni-grid-item>
					<text class="text">文本</text>
				</uni-grid-item>
				<uni-grid-item>
					<text class="text">文本</text>
				</uni-grid-item>
				<uni-grid-item>
					<text class="text">文本</text>
				</uni-grid-item>
				<uni-grid-item>
					<text class="text">文本</text>
				</uni-grid-item>
				<uni-grid-item>
					<text class="text">文本</text>
				</uni-grid-item>
			</uni-grid>
			<uni-section :title="'每行显示'+ column +'个(不能动态获取)'" type="line"></uni-section>
			<view class="show-column">
				<button class="show-column" @click="showColumnM">增加</button>
				<button class="show-column" @click="showColumnL">减少</button>
			</view>
			<uni-section title="边框展示" type="line"></uni-section>
			<uni-grid :column="column" :showBorder="false">
				<uni-grid-item>
					<text class="text">文本</text>
				</uni-grid-item>
				<uni-grid-item>
					<text class="text">文本</text>
				</uni-grid-item>
				<uni-grid-item>
					<text class="text">文本</text>
				</uni-grid-item>
				<uni-grid-item>
					<text class="text">文本</text>
				</uni-grid-item>
				<uni-grid-item>
					<text class="text">文本</text>
				</uni-grid-item>
				<uni-grid-item>
					<text class="text">文本</text>
				</uni-grid-item>
			</uni-grid>
			
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
				cpntitle: 'uni-grid 宫格',
				cpnDescrbe: "Grid 宫格组件，提供移动端常见的宫格布局，如九宫格。",
				cpnName: "uni-grid",
				number: 5.2,
				column:"3",
				showBorder:true
			}
		},
		components: {
			cpninfo
		},
		methods: {
			showColumnM(){
				this.column++
			},
			showColumnL(){
				this.column--
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
	
	.text{
		display: flex;
		justify-content: center;
		align-items: center;
	}
	
	.show-column{
		display: flex;
		flex-direction: row;
	}
</style>
