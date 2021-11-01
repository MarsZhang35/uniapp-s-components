<template>
	<view class="container">
		<view class="container-top">
			<view class="title">
				uni-drawer 抽屉
			</view>
			<view class="description">
				抽屉式导航，用于展示侧滑菜单，侧滑导航。通过数据驱动的单选框和复选框
			</view>
			<view class="author">
				<view class="author-detail">
					作者： DCloud前端团队
				</view>
				<image class="logo-image" src="/static/logo.png"></image>
			</view>
			插件ID：uni-drawer <br>
			插件包体积：4.9KB
			<view class="git-info">
				<image class="git-image" src="/static/git.png"></image>
				<uni-link href="https://github.com/dcloudio/uni-ui" text="https://github.com/dcloudio/uni-ui">
				</uni-link>
			</view>
		</view>
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
	export default {
		data() {
			return {
				maskClick:false,
				modes:"left"
			}
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
	
	.modes-view{
		display: flex;
		flex-direction: row;
	}
</style>
