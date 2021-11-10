<template>
	<view class="container">
		<view class="container-top">
			<view class="title">
				uni-grid 宫格
			</view>
			<view class="description">
				Grid 宫格组件，提供移动端常见的宫格布局，如九宫格。
			</view>
			<view class="author">
				<view class="author-detail">
					作者： DCloud前端团队
				</view>
				<image class="logo-image" src="/static/logo.png"></image>
			</view>
			插件ID：uni-grid <br>
			插件包体积：5.2KB
			<view class="git-info">
				<image class="git-image" src="/static/git.png"></image>
				<uni-link href="https://github.com/dcloudio/uni-ui" text="https://github.com/dcloudio/uni-ui">
				</uni-link>
			</view>
		</view>
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
	export default {
		data() {
			return {
				column:"3",
				showBorder:true
			}
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
		margin-bottom: 5rpx;
	}

	.description {
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.author {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		width: 55%;
	}

	.author-detail {}

	.logo-image {
		width: 40rpx;
		height: 40rpx;
	}

	.git-info {
		display: flex;
		flex-direction: row;
	}

	.git-image {
		width: 40rpx;
		height: 40rpx;
		padding-right: 10rpx;
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
