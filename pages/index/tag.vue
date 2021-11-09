<template>
	<view class="container">
		<view class="container-top">
			<view class="title">
				uni-tag 标签
			</view>
			<view class="description">
				Tag 组件，用于展示1个或多个文字标签，可点击切换选中、不选中的状态。
			</view>
			<view class="author">
				<view class="author-detail">
					作者： DCloud前端团队
				</view>
				<image class="logo-image" src="/static/logo.png"></image>
			</view>
			插件ID：uni-tag <br>
			插件包体积：4.2KB
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
			<view>
				<uni-section title="实心标签" type="line"></uni-section>
				<uni-tag :disabled="disabled" :inverted="inverted" text="标签" />
				<uni-tag :disabled="disabled" :inverted="inverted" text="标签" type="primary" @click="setInverted" />
				<uni-tag :disabled="disabled" :inverted="inverted" text="标签" type="success" @click="setInverted" />
				<uni-tag :disabled="disabled" :inverted="inverted" text="标签" type="warning" @click="setInverted" />
				<uni-tag :disabled="disabled" :inverted="inverted" text="标签" type="error" @click="setInverted" />
			</view>
			<view>
				<uni-section title="空心标签" type="line"></uni-section>
				<uni-tag :disabled="disabled" :inverted="inverted" text="标签" @click="setInverted" />
				<uni-tag :disabled="disabled" :inverted="inverted" text="标签" type="primary" @click="setInverted" />
				<uni-tag :disabled="disabled" :inverted="inverted" text="标签" type="success" @click="setInverted" />
				<uni-tag :disabled="disabled" :inverted="inverted" text="标签" type="warning" @click="setInverted" />
				<uni-tag :disabled="disabled" :inverted="inverted" text="标签" type="error" @click="setInverted" />
			</view>
			<view>
				<uni-section title="圆角样式" type="line"></uni-section>
				<uni-tag :disabled="disabled" :inverted="inverted" :circle="true" text="标签" type="primary" size="small"
					@click="setInverted" />
				<uni-tag :disabled="disabled" :inverted="inverted" :circle="true" text="标签" type="success" size="small"
					@click="setInverted" />
				<uni-tag :disabled="disabled" :inverted="inverted" :circle="true" text="标签" type="warning"
					@click="setInverted" />
				<uni-tag :disabled="disabled" :inverted="inverted" :circle="true" text="标签" type="error"
					@click="setInverted" />
			</view>
			<view>
				<uni-section title="自定义样式" type="line"></uni-section>
				<uni-tag :disabled="disabled" :inverted="inverted" :circle="true" type="primary" text="自定义样式" @click="setInverted" />
			</view>
			<uni-section title="禁用状态" type="line"></uni-section>
			<view class="change-disable">
				<button class="change-disable" @click="changeDisable">禁用/非禁用</button>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				inverted: false,
				disabled: false
			}
		},
		methods: {
			setInverted() {
				this.inverted = !this.inverted;
			},
			changeDisable() {
				this.disabled = !this.disabled;
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
</style>
