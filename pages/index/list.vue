<template>
	<view class="container">
		<view class="container-top">
			<view class="title">
				uni-list 列表
			</view>
			<view class="description">
				List 组件 ，帮助使用者快速构建列表。
			</view>
			<view class="author">
				<view class="author-detail">
					作者： DCloud前端团队
				</view>
				<image class="logo-image" src="/static/logo.png"></image>
			</view>
			插件ID：uni-list <br>
			插件包体积：17.3KB
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
			<uni-list>
				<uni-list-item :link="link" :to="to" :show-arrow="showarrow" :thumb="thumb" :show-switch="showSwitch" badgeText="100"
					:show-badge="showbadge" :disabled="disabled" title="列表文字" :note="note">
				</uni-list-item>
			</uni-list>
			<uni-section title="是否引用" type="line"></uni-section>
			<view class="disabled-view">
				<button class="disabled" @click="disAbled">禁用</button>
				<button class="disabled" @click="showBadge">引用角标</button>
				<button class="disabled" @click="showsSwitch">引开关</button>
				<button class="disabled" @click="showpicture">引图片</button>
			</view>
			<uni-section title="跳转页面(有箭头时生效)" type="line"></uni-section>
			<view class="disabled-view">
				<button class="use" @click="arrowR">右侧箭头</button>
				<button class="use" @click="showNote">是否显示note</button>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				disabled: false,
				showbadge: false,
				showSwitch: false,
				thumb: '',
				showarrow: false,
				link:"",
				to:'',
				note:""
			}
		},
		methods: {
			disAbled() {
				this.disabled = !this.disabled
			},
			showBadge() {
				this.showbadge = !this.showbadge
			},
			showsSwitch() {
				this.showSwitch = !this.showSwitch
			},
			showpicture() {
				if (this.thumb === '') {
					this.thumb = '/static/c1.png'
				} else {
					this.thumb = ''
				}
			},
			arrowR() {
				this.showarrow = !this.showarrow
				this.link = "reLaunch"
				this.to = '/pages/index/index'
			},
			showNote(){
				if(this.note === ""){
					this.note = "列表描述信息"
				}else{
					this.note = ""
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

	.disabled-view {
		display: flex;
		flex-direction: row;
	}
</style>
