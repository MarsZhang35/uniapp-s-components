<template>
	<view>
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
		<view class="container-bottom">
			<view class="title">
				概述
			</view>
			<uni-section title="基础图片" type="line">
			<view class="switch-container">
				<view v-show="show">
					显示图标名
				</view>
				<view v-show="!show">
					显示unicode
				</view>
				<switch class="control-switch" color="#205cf4" @change="changeName" />
			</view>
			</uni-section>
			<view class="icons-container">
				<!-- <uni-icons v-for="(item,index) in allIcon" :type="item.name" :color="item.color" :key="item.name"
					size="30" @click="changeColor(item)">{{}}</uni-icons> -->
				<view class="icons-icons" v-for="(item,index) in allIcon" :key="item.name" @click="changeColor(item)">
					<uni-icons :type="item.name" :color="item.color" size="30">
					</uni-icons>
					<view class="icons-font" v-show="show">
						{{item.name}}
					</view>
					<view class="icons-font" v-show="!show">
						{{item.unicode}}
					</view>
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
				cpntitle: 'uni-icons 图标',
				cpnDescrbe: "图标组件，用于展示移动端常见的图标，可自定义颜色、大小。",
				cpnName: "uni-icons",
				number: 40,
				show: true,
				allIcon: [{
					name: 'arrowdown',
					color: '#7c7c82',
					unicode: 'e581'
				}, {
					name: "arrowleft",
					color: '#7c7c82',
					unicode: 'e582'
				}, {
					name: "arrowright",
					color: '#7c7c82',
					unicode: 'e583'
				}, {
					name: "arrowup",
					color: '#7c7c82',
					unicode: 'e580'
				}, {
					name: 'arrowthindown',
					color: '#7c7c82',
					unicode: 'e585'
				}, {
					name: "arrowthinleft",
					color: '#7c7c82',
					unicode: 'e586'
				}, {
					name: "arrowthinright",
					color: '#7c7c82',
					unicode: 'e587'
				}, {
					name: "arrowthinup",
					color: '#7c7c82',
					unicode: 'e584'
				}, {
					name: "back",
					color: '#7c7c82',
					unicode: 'e471'
				}, {
					name: "forward",
					color: '#7c7c82',
					unicode: 'e470'
				}, {
					name: "camera",
					color: '#7c7c82',
					unicode: 'e301'
				}, {
					name: "camera-filled",
					color: '#7c7c82',
					unicode: 'e7ef'
				}]
			}
		},
		components: {
			cpninfo
		},
		methods: {
			changeName() {
				this.show = !this.show
			},
			changeColor(item) {
				if (item.color === '#7c7c82') {
					item.color = '#2266ff'
				} else {
					item.color = '#7c7c82'
				}
			}
		}
	}
</script>

<style>
	.title {
		width: 100%;
		font-size: 50rpx;
		font-weight: bold;
		background-color: #6fdbdd;
		display: flex;
		justify-content: center;
		align-items: flex-start;
	}

	.switch-container {
		display: flex;
		justify-content: flex-end;
		align-items: center;
	}

	.control-switch{
		padding: 0 20rpx;
	}
	
	.icons-container {
		padding: 20rpx;
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		justify-content: space-around;
		align-content: space-around;
	}

	.icons-icons {
		width: 200rpx;
		height: 150rpx;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}

	.icons-font {
		font-size: 30rpx;
		color: '#7c7c82'
	}
</style>
