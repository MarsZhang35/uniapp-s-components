<template>
	<view>
		<view class="container-top">
			<view class="title">
				{{cpntitle}}
				<!-- uni-badge 数字角标 -->
			</view>
			<view class="description">
				{{cpnDescrbe}}
				<!-- view数字角标（徽章）组件，在元素周围展示消息提醒，一般用于列表、九宫格、按钮等地方。 -->
			</view>
			<view class="author">
				<view class="author-detail">
					作者： DCloud前端团队 已实名认证
				</view>
				<image class="logo-image" src="/static/logo.png"></image>
			</view>
			插件ID：{{cpnName}} <br>
			插件包体积：{{number}}KB
			<view class="git-info">
				<image class="git-image" src="/static/git.png"></image>
				<uni-link href="https://github.com/dcloudio/uni-ui" text="https://github.com/dcloudio/uni-ui">
				</uni-link>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		//name:"publicpn",
		data() {
			return {
				
			}
		},
		props:{
			cpntitle:{
				type:String,
				default: ''
			},
			cpnDescrbe:{
				type:String,
				default: ''
			},
			cpnName:{
				type:String,
				default: ''
			},
			number:{
				type:Number,
				default: 0
			}
		},
		methods: {
			
		}
	}
</script>

<style scoped>
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
		background-color: #f7f7f7;
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
		width: 85%;
	}

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
</style>
