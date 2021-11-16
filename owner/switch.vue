<template>
	<view>
		<view class="container-top">
			<view class="title">
				switch 开关
			</view>
			<view class="description">
				开关选择器。
			</view>
		</view>
		<uni-section class="u-section" title="简单展示" type="line"></uni-section>
		<view>
			<view >
				<view>默认样式</view>
				<view>
					<switch checked @change="switch1Change" />
					<switch @change="switch2Change" />
				</view>
				<view>推荐展示样式</view>
				<switch checked  color="#0000FF" type="checkbox"/>
				<switch class="active" checked  color="#0000FF"/>
			</view>
			<view>
				<view>
					<view>开启中</view>
					<switch checked/>
				</view>
				<view>
					<view>关闭</view>
					<switch/>
				</view>
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
			switch1Change: function(e) {
				console.log('switch1 发生 change 事件，携带值为', e.target.value)
			},
			switch2Change: function(e) {
				console.log('switch2 发生 change 事件，携带值为', e.target.value)
			}
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
		align-items: center;
	}

	.title {
		width: 100%;
		font-size: 50rpx;
		font-weight: bold;
		background-color: #6fdbdd;
		display: flex;
		justify-content: center;
		align-items: center;
	}

</style>
