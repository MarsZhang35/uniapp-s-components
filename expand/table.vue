<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
		<view class="container-bottom">
			<view class="title">
				概述
			</view>
			<uni-table :border="border" :stripe="stripe" type="selection" emptyText="暂无更多数据" :loading="loading">
				<!-- 表头行 -->
				<uni-tr>
					<uni-th align="center">日期</uni-th>
					<uni-th align="center">姓名</uni-th>
					<uni-th align="left">地址</uni-th>
				</uni-tr>
				<!-- 表格数据行 -->
				<uni-tr>
					<uni-td>2021-11-09</uni-td>
					<uni-td>Mars</uni-td>
					<uni-td>上海市黄浦区</uni-td>
					<t-td align="left"><button @click="edit()">编辑</button></t-td>
				</uni-tr>
				<uni-tr>
					<uni-td>2021-11-09</uni-td>
					<uni-td>Feng</uni-td>
					<uni-td>上海市徐汇区</uni-td>
					<t-td align="left"><button @click="edit()">编辑</button></t-td>
				</uni-tr>
				<uni-tr>
					<uni-td>2021-11-09</uni-td>
					<uni-td>Zhang</uni-td>
					<uni-td>上海市浦东新区</uni-td>
					<t-td align="left"><button @click="edit()">编辑</button></t-td>
				</uni-tr>
			</uni-table>
			<uni-section title="结构调整" type="line"></uni-section>
			<view class="change-border-view">
				<button class="change-border" @click="changeBorder">显示/隐藏竖线(无效)</button>
				<button class="change-loading" @click="changeLoading">载入/未载入</button>
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
				cpntitle: 'uni-table 表格',
				cpnDescrbe: "表格组件，多用于展示多条结构类似的数据",
				cpnName: "uni-table",
				number: 16.8,
				border: false,
				loading: false,
				stripe: true,
			}
		},
		components: {
			cpninfo
		},
		methods: {
			edit() {
				uni.showToast({
					title: "欢迎编辑",
					icon: 'none'
				});
			},
			changeBorder() {
				this.border = !this.border
			},
			changeLoading(){
				this.loading = !this.loading
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
