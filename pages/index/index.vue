<template>
	<view class="container">
		<uni-section class="u-section" title="自带组建" type="line"></uni-section>
		<view class="goto-page" @click="myNavigator('/owner/view')">
			view 视图容器
		</view>
		<view class="goto-page" @click="myNavigator('/owner/map')">
			map 地图
		</view>
		<view class="goto-page" @click="myNavigator('/owner/canvas')">
			canvase 画布
		</view>
		<uni-section class="u-section" title="扩展组建" type="line"></uni-section>
		<view class="goto-page" @click="myNavigator('/subpkg/badge')">
			uni-badge 数字角标
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/calendar')">
			uni-calendar 日历
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/card')">
			uni-calendar 卡片
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/collapse')">
			uni-calendar 折叠面板
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/combox')">
			uni-combox 组合框
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/countDown')">
			uni-countdown 倒计时 
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/dataCheckbox')">
			uni-data-checkbox 数据选择器
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/dataPicker')">
			uni-data-picker 数据驱动的picker选择器
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/datetimePicker')">
			uni-datetime-picker 日期选择器
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/drawer')">
			uni-drawer 抽屉
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/easyInput')">
			uni-easyinput 增强输入框
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/fab')">
			uni-fab 悬浮按钮
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/fav')">
			uni-fav 收藏按钮
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/filePicker')">
			uni-file-picker 文件选择上传
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/forms')">
			uni-forms 表单
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/goodsNav')">
			uni-goods-nav 商品导航
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/grid')">
			uni-grid 宫格
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/group')">
			uni-group 分组 
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/indexedList')">
			uni-indexed-list 索引列表
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/list')">
			20.uni-list 列表
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/loadMore')">
			uni-load-more 加载更多
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/navBar')">
			uni-nav-bar 自定义导航栏
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/noticeBar')">
			uni-notice-bar 通告栏
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/numberBox')">
			uni-number-box 数字输入框
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/pagination')">
			25.uni-pagination 分页器
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/popup')">
			uni-popup 弹出层
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/rate')">
			uni-rate 评分
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/searchBar')">
			uni-search-bar 搜索栏
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/segmentedControl')">
			uni-segmented-control 分段器
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/steps')">
			30.uni-steps 步骤条
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/swipeAction')">
			uni-swipe-action 滑动操作
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/swiperDot')">
			uni-swiper-dot 轮播图指示点
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/table')">
			uni-table 表格
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/tag')">
			uni-tag 标签
		</view>
		<view class="goto-page" @click="myNavigator('/subpkg/transition')">
			uni-transition 过渡动画
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
	
	.u-section{
		width: 100%;
	}
	
	.goto-page{
		width: 98%;
		/* border: 1rpx black solid; */
		display: flex;
		justify-content: center;
		align-items: center;
		background-color: #459bff;
		margin: 5rpx 0;
	}
</style>
