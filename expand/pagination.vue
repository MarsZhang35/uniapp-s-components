<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
		<view class="container-bottom-view">
			<view class="title">
				概述
			</view>
			<uni-pagination :current="current" :total="total" :show-icon="showicon" @change="change" />
			<text>当前页：{{ current }}，数据总量：{{ total }}条，每页数据：{{ pageSize }}</text>
			<button type="primary" @click="add">增加</button>
			<button type="default" @click="reset">重置数据</button>
			<uni-section title="切换" type="line"></uni-section>
			<view class="change-view">
				<button class="change" @click="changeIcon">切换图标</button>
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
				cpntitle: 'uni-pagination 分页器',
				cpnDescrbe: "Pagination 分页器组件，用于展示页码、请求数据等。",
				cpnName: "uni-pagination",
				number: 6.4,
				showicon: "true",
				current: 1,
				total: 0,
				pageSize: 10
			}
		},
		components: {
			cpninfo
		},
		methods: {
			changeIcon() {
				this.showicon = !this.showicon
			},
			add() {
				this.total += 10;
			},
			reset() {
				this.total = 0;
				this.current = 1;
			},
			change(e) {
				this.current = e.current;
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
