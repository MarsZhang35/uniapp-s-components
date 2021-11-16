<template>
	<view class="container-top">
		<view class="title">
			text 文字
		</view>
		<view class="description">
			文本组件：用于包裹文本内容。
		</view>
		<uni-section class="u-section" title="简单展示" type="line"></uni-section>
		<view>
			<view class="padding-wrap">
				<view class="text-box" scroll-y="true">
					<text>{{text}}</text>
				</view>
			</view>
		</view>
		<view class="uni-btn">
			<button type="primary" :disabled="!canAdd" @click="add">add line</button>
			<button type="warn" :disabled="!canRemove" @click="remove">remove line</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				texts: [
					'HBuilder，500万开发者选择的IDE',
					'MUI，轻巧、漂亮的前端开源框架',
					'wap2app，M站快速转换原生体验的App',
					'5+Runtime，为HTML5插上原生的翅膀',
					'HBuilderX，轻巧、极速，极客编辑器',
					'uni-app，终极跨平台方案',
					'HBuilder，500万开发者选择的IDE',
					'MUI，轻巧、漂亮的前端开源框架',
					'wap2app，M站快速转换原生体验的App',
					'5+Runtime，为HTML5插上原生的翅膀',
					'HBuilderX，轻巧、极速，极客编辑器',
					'uni-app，终极跨平台方案',
					'......',
					'一年 10000',
					'一个月840',
					'一周210',
					'一周 200（住） + 20（手机） + 60（行） + 420（食） = 720 ',
				],
				text: '',
				canAdd: true,
				canRemove: false,
				extraLine: []
			}
		},
		methods: {
			add: function(e) {
				this.extraLine.push(this.texts[this.extraLine.length % 12]);
				this.text = this.extraLine.join('\n');
				this.canAdd = this.extraLine.length < 12;
				this.canRemove = this.extraLine.length > 0;
			},
			remove: function(e) {
				if (this.extraLine.length > 0) {
					this.extraLine.pop();
					this.text = this.extraLine.join('\n');
					this.canAdd = this.extraLine.length < 12;
					this.canRemove = this.extraLine.length > 0;
				}
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

	.u-section {
		width: 100%;
	}

	.padding-wrap {
		width: 100%;
	}

	.text-box {
		height: 600rpx;
	}

	.uni-btn {
		width: 100%;
	}
</style>
