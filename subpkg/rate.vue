<template>
	<view class="container">
		<view class="container-top">
			<view class="title">
				uni-rate 评分
			</view>
			<view class="description">
				Rate 评分组件，可自定义评分星星图标的大小、间隔、评分数。
			</view>
			<view class="author">
				<view class="author-detail">
					作者： DCloud前端团队
				</view>
				<image class="logo-image" src="/static/logo.png"></image>
			</view>
			插件ID：uni-rate <br>
			插件包体积：6.2KB
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
			<uni-section title="正常显示" type="line"></uni-section>
			<uni-rate v-model="value" />

			<uni-section title="不支持滑动手势选择评分" type="line"></uni-section>
			<uni-rate :touchable="false" :value="5" />

			<uni-section title="设置尺寸大小" type="line"></uni-section>
			<uni-rate :size="18" :value="5" />

			<uni-section title="设置评分数" type="line"></uni-section>
			<uni-rate :max="10" :value="5" />

			<uni-section title="设置星星间隔" type="line"></uni-section>
			<uni-rate :value="4" :margin="20" />

			<uni-section title="设置颜色" type="line"></uni-section>
			<uni-rate :value="3" color="#bbb" active-color="red" />

			<uni-section title="选择半星" type="line"></uni-section>
			<uni-rate allow-half :value="3.5" />

			<uni-section title="只读状态" type="line"></uni-section>
			<uni-rate :readonly="true" :value="2" />

			<uni-section title="禁用状态" type="line"></uni-section>
			<uni-rate :disabled="true" disabledColor="#ccc" :value="3" />

			<uni-section title="未选中的星星为镂空状态" type="line"></uni-section>
			<uni-rate :value="3" :is-fill="false" />
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				value: 1
			}
		},
		methods: {

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
</style>
