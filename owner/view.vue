<template>
	<view class="container-top">
		<view class="title">
			view 视图容器
		</view>
		<view class="description">
			它类似于传统html中的div，用于包裹各种元素内容。
		</view>
		<uni-section class="line" title="实操" type="line"></uni-section>
		<view class="uni-view">
			<view class="uni-view-row">
				flex-direction: row
				<text>\n横向布局</text>
			</view>
			<view class="uni-flex-row">
				<view class="flex-item-red">A</view>
				<view class="flex-item-green">B</view>
				<view class="flex-item-blue">C</view>
			</view>
			<view class="uni-view-column">
				flex-direction: column
				<text>\n纵向布局</text>
			</view>
			<view class="uni-flex-column">
				<view class="flex-item-red">A</view>
				<view class="flex-item-green">B</view>
				<view class="flex-item-blue">C</view>
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
	
	.line{
		width: 100%;
	}
	
	.uni-view{
		width: 100%;
	}
	
	.uni-flex-row{
		
		display: flex;
		flex-direction: row;
		width: 100%;
		height: 200rpx;
	}
	
	.flex-item-red{
		display: flex;
		justify-content: center;
		align-items: center;
		flex: 1;
		background-color: #f34a4e;
		color: #FFFFFF;
	}
	.flex-item-green{
		display: flex;
		justify-content: center;
		align-items: center;
		flex: 1;
		background-color: #2eb208;
		color: #FFFFFF;
	}
	.flex-item-blue{
		display: flex;
		justify-content: center;
		align-items: center;
		flex: 1;
		background-color: #2160ff;
		color: #FFFFFF;
	}
	
	.uni-flex-column{
		display: flex;
		flex-direction: column;
		height: 600rpx;
	}
</style>
