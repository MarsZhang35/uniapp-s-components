<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
		<view class="container-bottom-view">
			<view class="title">
				概述
			</view>
			<uni-fab :pattern="pattern" :content="content" :horizontal="horizontal" :vertical="vertical" :direction="direction"
				:popMenu="true"  @trigger="trigger"/>
			<view class="container-bottom">
				<!-- <uni-section title="改变颜色" type="line"></uni-section> -->
				<view class="change">
					<button class="change-color" @click="changeColor">改变按钮颜色</button>
					<button class="changeHV" @click="changeHV">切换菜单水平/垂直</button>
				</view>
				<uni-section title="改变位置" type="line"></uni-section>
				<view class="change-postion-view">
					<button class="change-postion-view" @click="changetoLB">显示在左下角</button>
					<button class="change-postion-view" @click="changetoRB">显示在有下角</button>
					<button class="change-postion-view" @click="changetoLT">显示在左上角</button>
					<button class="change-postion-view" @click="changetoRT">显示在右上角</button>
				</view>
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
				cpntitle: 'uni-fab 悬浮按钮',
				cpnDescrbe: "悬浮按钮 fab button ，点击可展开一个图标按钮菜单。",
				cpnName: "uni-fab",
				number: 8,
				direction:"horizontal",
				horizontal:"left",
				vertical:"bottom",
				pattern: {
					buttonColor: "#007AFF"
				},
				content: [{
						iconPath: '/static/component.png',
						selectedIconPath: '/static/componentHL.png',
						text: '组件',
						active: true
					},
					{
						iconPath: '/static/api.png',
						selectedIconPath: '/static/apiHL.png',
						text: 'API',
						active: true
					},
					{
						iconPath: '/static/template.png',
						selectedIconPath: '/static/templateHL.png',
						text: '模版',
						active: false
					}
				]
			}
		},
		components: {
			cpninfo
		},
		methods: {
			changeColor() {
				const rgb = []
				for (let i = 0; i < 3; ++i) {
					let color = Math.floor(Math.random() * 256).toString(16)
					color = color.length == 1 ? '0' + color : color
					rgb.push(color)
				}
				this.pattern.buttonColor = '#' + rgb.join('')
			},
			trigger(e) {
				uni.showModal({
					title: '提示',
					content: `选中项：${e.item.text}`,
				});
			},
			changeHV(){
				if(this.direction === "horizontal"){
					this.direction = "vertical"
				}else{
					this.direction = "horizontal"
				}
			},
			changetoLB(){
				this.horizontal = "left",
				this.vertical = "bottom"
			},
			changetoRB(){
				this.horizontal = "right",
				this.vertical = "bottom"
			},
			changetoLT(){
				this.horizontal = "left",
				this.vertical = "top"
			},
			changetoRT(){
				this.horizontal = "right",
				this.vertical = "top"
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
	.container-bottom {
		display: flex;
		flex-direction: column;

		align-items: center;
	}
</style>
