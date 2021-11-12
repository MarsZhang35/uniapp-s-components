<template>
	<view>
		<view class="container-top">
			<view class="title">
				slider 滑块
			</view>
			<view class="description">
				获取当前位置
			</view>
		</view>
		<uni-section class="u-section" title="简单展示" type="line"></uni-section>
		<view>
			<view class="uni-wrap">
				<view class="uni-title">设置step</view>
				<view>
					<slider class="active" value="60" @change="sliderChange" step="5" />
				</view>
				<view class="uni-title">显示当前value</view>
				<view>
					<slider value="50" @change="sliderChange" show-value />
				</view>

				<view class="uni-title">设置最小/最大值</view>
				<view>
					<slider value="100" @change="sliderChange" min="50" max="200" show-value />
				</view>

				<view class="uni-title">不同颜色和大小的滑块</view>
				<view>
					<slider value="50" @change="sliderChange" activeColor="#FFCC33" backgroundColor="#000000"
						block-color="#8A6DE9" block-size="20" />
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {
			sliderChange(e) {
				console.log('value 发生变化：' + e.detail.value)
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

	.u-section {
		width: 100%;
	}

	.uni-wrap {
		width: 100%;
	}

	.uni-title {
		width: 100%;
	}
</style>
