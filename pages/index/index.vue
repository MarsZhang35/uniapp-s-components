<template>
	<view class="whole-page">
		<view class="container">
			<image class="top-image" src="/static/component.png" mode=""></image>
			<text>uni-app内置组件</text>
		</view>
		<view class="main-container">
			<uni-collapse class="u-collapse" :accordion="accordion">
				<uni-collapse-item class="first-collapse" title="视图容器">
					<view class="goto-page" @click="myNavigator('/owner/view')">
						view 视图容器
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="覆盖">
					<view class="goto-page" @click="myNavigator('/owner/coverView')">
						cover-view 覆盖
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="视频">
					<view class="goto-page" @click="myNavigator('/owner/video')">
						video 视频
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="地图">
					<view class="goto-page" @click="myNavigator('/owner/map')">
						map 地图
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="滑块">
					<view class="goto-page" @click="myNavigator('/owner/slider')">
						slider 滑块
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="开关">
					<view class="goto-page" @click="myNavigator('/owner/switch')">
						switch 开关
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="画布">
					<view class="goto-page" @click="myNavigator('/owner/canvas')">
						canvas 画布
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="文字">
					<view class="goto-page" @click="myNavigator('/owner/text')">
						text 文字
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="进度条">
					<view class="goto-page" @click="myNavigator('/owner/progress')">
						progress 进度条
					</view>
				</uni-collapse-item>
			</uni-collapse>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				accordion: true,
				searchValue: "",
			}
		},
		methods: {
			myNavigator(path) {
				uni.navigateTo({
					url: path
				})
			},
			search(e){
				
			}
		},
	}
</script>

<style>
	page {
		background-color: #f7f7f7;
	}

	.whole-page {
		display: flex;
		flex-direction: column;
		flex: 1;
	}

	.container {
		display: flex;
		flex: 2;
		justify-content: center;
		align-items: center;
		flex-direction: column;
	}

	.top-image {
		width: 150rpx;
		height: 150rpx;
	}

	.main-container {
		padding: 20rpx;
		display: flex;
		flex-direction: column;
		flex: 8;
	}

	.u-collapse {
		margin: 15rpx 0;
	}

	.goto-page {
		height: 40rpx;
		padding: 10rpx 40rpx;
	}

	.first-collapse {
		background-color: #FFFFFF;
	}
</style>
