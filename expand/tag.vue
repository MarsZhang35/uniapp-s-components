<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
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
	import {
		cpninfo,
		cpntitle,
		cpnDescrbe,
		cpnName,
		number
	} from '../component/cpninfo.vue'
	export default {
		data() {
			return {
				cpntitle: 'uni-tag 标签',
				cpnDescrbe: "Tag 组件，用于展示1个或多个文字标签，可点击切换选中、不选中的状态。",
				cpnName: "uni-tag",
				number: 4.2,
				inverted: false,
				disabled: false
			}
		},
		components: {
			cpninfo
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

	.title{
		width: 100%;
		font-size: 50rpx;
		font-weight: bold;
		background-color: #6fdbdd;
		display: flex;
		justify-content: center;
		align-items: flex-start;
	}
</style>
