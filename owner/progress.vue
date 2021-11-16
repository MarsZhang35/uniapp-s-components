<template>
	<view>
		<view class="container-top">
			<view class="title">
				progress 进度条
			</view>
			<view class="description">
				进度条
			</view>
		</view>
		<uni-section class="u-section" title="简单展示" type="line"></uni-section>
		<view class="active">
			<view class="progress-box">
				<progress :percent="pgList[0]" show-info stroke-width="3" />
			</view>
			<view class="progress-box">
				<progress :percent="pgList[1]" stroke-width="3" />
			</view>
			<view class="progress-box">
				<progress :percent="pgList[2]" active stroke-width="3" />
			</view>
			<view v-show="show">
				我是第一次问题
			</view>
			<view v-show="showSecond">
				我是第二次问题
			</view>
			<view v-show="showThird">
				我是第三次问题
			</view>
			<view class="progress-box">
				<progress :percent="percent" active active-mode="forwards" activeColor="#10AEFF" backgroundColor="#0000FF" stroke-width="6" />
			</view>
		</view>
		<button type="primary" @click="setProgress">设置进度</button>
		<button type="warn" @click="clearProgress">清除进度</button>
		<button v-show="show" type="primary" @click="firstProgress">第一次</button>
		<button v-show="showSecond" type="primary" @click="secondProgress">第二次</button>
		<button v-show="showThird" type="primary" @click="thirdProgress">第三次</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				pgList: [0, 0, 0],
				percent:0,
				show:true,
				showSecond:false,
				showThird:false
			}
		},
		methods: {
			setProgress() {
				this.pgList = [20, 40, 60]
			},
			clearProgress() {
				this.pgList = [0, 0, 0]
			},
			firstProgress(){
				this.percent = 33.33
				this.show = false
				this.showSecond = true
			},
			secondProgress(){
				this.percent = 66.66
				this.showSecond = false
				this.showThird = true
			},
			thirdProgress(){
				this.percent = 99.99
			}
		}
	}
</script>

<style>
	.container-top {
		display: flex;
		justify-content: center;
		align-items: flex-start;
		flex-direction: column;
		padding: 20rpx;
		align-items: center;
	}

	.title {
		width: 100%;
		font-size: 50rpx;
		font-weight: bold;
		background-color: #6fdbdd;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.active{
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
	}
	
	.progress-box {
		margin: 20rpx 0;
		width: 90%;
	}
</style>
