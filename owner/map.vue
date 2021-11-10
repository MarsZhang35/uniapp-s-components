<template>
	<view class="container-top">
		<view class="title">
			map 地图组建
		</view>
		<view class="description">
			地图组件用于展示地图，而定位API只是获取坐标，请勿混淆两者。
		</view>
		<map style="width: 100%; height: 300px;" :latitude="latitude" :longitude="longitude" :markers="covers">
		</map>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				id: 0, // 使用 marker点击事件 需要填写id
				title: 'map',
				latitude: 39.909,
				longitude: 116.39742,
				covers: [{
					latitude: 39.909,
					longitude: 116.39742,
				}, {
					latitude: 39.90,
					longitude: 116.39,
				}]
			}
		},
		methods: {

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
	}

	.title {
		width: 100%;
		font-size: 50rpx;
		font-weight: bold;
		background-color: #6fdbdd;
		display: flex;
		justify-content: center;
		align-items: flex-start;
	}
</style>
