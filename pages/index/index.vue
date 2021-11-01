<template>
	<view class="container">
		<view class="goto-page" @click="myNavigator('/pages/index/badge')">
			uni-badge 数字角标
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/card')">
			uni-calendar 卡片
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/collapse')">
			uni-calendar 折叠面板
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/combox')">
			uni-combox 组合框
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/countDown')">
			CountDown 倒计时
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/dataCheckbox')">
			uni-data-checkbox 数据选择器
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/dataPicker')">
			uni-data-picker 数据驱动的picker选择器
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/datetimePicker')">
			uni-datetime-picker 日期选择器
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/drawer')">
			uni-drawer 抽屉
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/easyInput')">
			uni-easyinput 增强输入框
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/fab')">
			uni-fab 悬浮按钮
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/fav')">
			uni-fav 收藏按钮
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/filePicker')">
			uni-file-picker 文件选择上传
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/forms')">
			uni-forms 表单
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/goodsNav')">
			uni-goods-nav 商品导航
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/grid')">
			uni-grid 宫格
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/group')">
			uni-group 分组 
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/indexedList')">
			uni-indexed-list 索引列表
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/list')">
			uni-list 列表
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/loadMore')">
			20.uni-load-more 加载更多
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/navBar')">
			uni-nav-bar 自定义导航栏
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/noticeBar')">
			uni-notice-bar 通告栏
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/numberBox')">
			uni-number-box 数字输入框
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/pagination')">
			uni-pagination 分页器
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/popup')">
			25.uni-popup 弹出层
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/rate')">
			uni-rate 评分
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/searchBar')">
			uni-search-bar 搜索栏
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/segmentedControl')">
			uni-segmented-control 分段器
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/steps')">
			uni-steps 步骤条
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/swipeAction')">
			30.uni-swipe-action 滑动操作
		</view>
		<view class="goto-page" @click="myNavigator('/pages/index/swiperDot')">
			uni-swiper-dot 轮播图指示点
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
			myNavigator(path) {
				uni.navigateTo({
					url: path
				})
			},
		}
	}
</script>

<style>
	.container {
		padding: 10px;
		font-size: 14px;
		line-height: 24px;
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
	}
	
	.goto-page{
		width: 98%;
		/* border: 1rpx black solid; */
		display: flex;
		justify-content: center;
		align-items: center;
		background-color: #69e1e8;
		margin: 5rpx 0;
	}
</style>
