<template>
	<view class="container">
		<view class="container-top">
			<view class="title">
				uni-file-picker 文件选择上传
			</view>
			<view class="description">
				文件选择上传组件，可以选择图片、视频等任意文件并上传到当前绑定的服务空间
			</view>
			<view class="author">
				<view class="author-detail">
					作者： DCloud前端团队
				</view>
				<image class="logo-image" src="/static/logo.png"></image>
			</view>
			插件ID：uni-file-picker <br>
			插件包体积：17.4KB
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
			最多选择{{limit}}张照片
			<uni-file-picker v-model="imageValue" :limit="limit" fileMediatype="image" mode="grid" />
			<uni-section title="最多显示多少张图片" type="line"></uni-section>
			<view class="show-pic">
				<button class="show-pic" @click="picinc">增加</button>
				<button class="show-pic" @click="picdec">减少</button>
			</view>
			<uni-section title="单选图片且点击再次选择" type="line"></uni-section>
			<uni-file-picker disable-preview :del-icon="false" return-type="object">选择头像</uni-file-picker>
			<uni-section title="上传文件" type="line"></uni-section>
			<uni-file-picker v-model="value" file-mediatype="all">
				<button>选择文件</button>
			</uni-file-picker>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				imageValue: [],
				limit: 9
			}
		},
		methods: {
			picinc() {
				if (this.limit <= 8) {
					this.limit++
				}
			},
			picdec() {
				if (this.limit >= 2) {
					this.limit--
				}
			}
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

	.show-pic {
		display: flex;
		flex-direction: row;
	}
</style>
