<template>
	<view>
		<!-- 顶部信息 -->
		<view class="topbg">
			<view class="top-image">
				<image class="info-image" src="/static/git.png" mode="heightFix"></image>
			</view>
			<view class="author-info">
				<view class="author-name">
					Mars.
				</view>
				<view class="manage-level">
					Vip:10
				</view>
			</view>
			<uni-icons class="top-gear" type="gear" color="#6fb881" size="35"
				@click="myNavigator('/aboutMe/setting')" />
		</view>
		<!-- 中部信息 -->
		<view class="mid-contain">
			<view class="info-view">
				<view class="info">
					我的信息
				</view>
				<view class="desc">
					<view class="desc-image-view" @click="nextPage('联系我')">
						<image class="desc-image" src="/static/connectMe.png" mode="heightFix"></image>
						<view>
							联系我
						</view>
					</view>
					<view class="desc-image-view" @click="nextPage('支持我')">
						<image class="desc-image" src="/static/supportMe.png" mode="heightFix"></image>
						<view>
							支持我
						</view>
					</view>
					<view class="desc-image-view" @click="nextPage('来找我')">
						<image class="desc-image" src="/static/location.png" mode="heightFix"></image>
						<view>
							来找我
						</view>
					</view>
				</view>
			</view>
			<view class="item" @click="goPage('意见反馈')">
				<uni-icons class="item-icons" type="chatboxes" color="#6fb881" size="30"></uni-icons>
				<view class="item-name">
					意见反馈
				</view>
			</view>
			<view class="item" @click="goPage('版权说明')">
				<uni-icons class="item-icons" type="info" color="#6fb881" size="30"></uni-icons>
				<view class="item-name">
					版权说明
				</view>
			</view>
		</view>
		<!-- <view class="tiny-button"  @click="myNavigator('/aboutMe/allImage')"></view> -->
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {
			nextPage(e) {
				if (e === '联系我') {
					this.myNavigator('/aboutMe/connectMe')
				} else if (e === '支持我') {
					this.myNavigator('/aboutMe/supportMe')
				} else {
					this.myNavigator('/aboutMe/location')
				}
			},
			goPage(e) {
				if (e === '意见反馈') {
					this.myNavigator('/aboutMe/feedBack')
				} else {
					this.myNavigator('/aboutMe/copyright')
				}
			},
			myNavigator(path) {
				uni.navigateTo({
					url: path
				})
			}
		}
	}
</script>

<style>
	page {
		background-color: #f7f7f7;
	}

	.topbg {
		width: 100%;
		height: 230rpx;
		background: linear-gradient(to bottom, #16505b, #6fb881);
		display: flex;
		flex-direction: row;
		padding: 50rpx;
		justify-content: flex-start;
	}

	.info-image {
		height: 180rpx;
	}

	.author-info {
		color: #FFFFFF;
		display: flex;
		justify-content: flex-start;
		align-items: flex-start;
		flex-direction: column;
		padding: 20rpx;
		flex: 0.85;
	}

	.author-name {
		font-size: 50rpx;
	}

	.manage-level {
		font-size: 30rpx;
		color: white;
		border: 2rpx solid #9b9b9b;
		border-radius: 40rpx;
		padding: 0 10rpx;
	}

	.top-gear {
		align-items: center;
		justify-content: center;
		padding: 20;
	}

	.mid-contain {
		display: flex;
		width: 100%;
		justify-content: center;
		align-items: center;
		flex-direction: column;
	}

	.info-view {
		width: 92%;
		height: 260rpx;
		background-color: #FFFFFF;
		border-radius: 20rpx;
		margin-top: -80rpx;
		display: flex;
		flex-direction: column;
		box-shadow: 0rpx 8rpx 8rpx 3rpx rgb(221, 220, 220);
	}

	.info {
		font-size: 44rpx;
		color: gray;
		text-align: left;
		height: 60rpx;
		padding: 25rpx;
	}

	.desc {
		color: grey;
		display: flex;
		flex-direction: row;
		font-size: 30rpx;
		justify-content: space-around;
	}

	.desc-image-view {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}

	.desc-image {
		width: 100rpx;
		height: 100rpx;
	}

	.item {
		width: 92%;
		height: 100rpx;
		display: flex;
		align-items: center;
		justify-content: flex-start;
		border-radius: 20rpx;
		box-shadow: 0rpx 8rpx 8rpx 3rpx rgb(221, 220, 220);
		/* background-color: #FFFFFF; */
	}

	.item-icons {
		flex: 1;
		padding: 20rpx;
	}

	.item-name {
		flex: 9;
	}
	
	.tiny-button{
		height: 100rpx;
		width: 100rpx;
	}
</style>
