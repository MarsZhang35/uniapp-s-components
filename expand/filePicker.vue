<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
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
				cpntitle: 'uni-file-picker 文件选择上传',
				cpnDescrbe: "文件选择上传组件，可以选择图片、视频等任意文件并上传到当前绑定的服务空间",
				cpnName: "uni-file-picker",
				number: 17.4,
				imageValue: [],
				limit: 9
			}
		},
		components: {
			cpninfo
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

	.title{
		width: 100%;
		font-size: 50rpx;
		font-weight: bold;
		background-color: #6fdbdd;
		display: flex;
		justify-content: center;
		align-items: flex-start;
	}

	.show-pic {
		display: flex;
		flex-direction: row;
	}
</style>
