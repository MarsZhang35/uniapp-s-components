<template>
	<view class="whole-page">
		<view class="container">
			<image class="top-image" src="/static/template.png" mode=""></image>
			<text>以下是uni-app扩展组件示例</text>
		</view>
		<view class="main-container">
			<uni-collapse class="u-collapse" :accordion="accordion">
				<uni-collapse-item class="first-collapse" title="数字角标">
					<view class="goto-page" @click="myNavigator('/expand/badge')">
						uni-badge 数字角标
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="日历">
					<view class="goto-page" @click="myNavigator('/expand/calendar')">
						uni-calendar 日历
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="卡片">
					<view class="goto-page" @click="myNavigator('/expand/card')">
						uni-calendar 卡片
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="折叠面板">
					<view class="goto-page" @click="myNavigator('/expand/collapse')">
						uni-calendar 折叠面板
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="组合框">
					<view class="goto-page" @click="myNavigator('/expand/combox')">
						uni-combox 组合框
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="倒计时">
					<view class="goto-page" @click="myNavigator('/expand/countDown')">
						uni-countdown 倒计时
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="数据选择器">
					<view class="goto-page" @click="myNavigator('/expand/dataCheckbox')">
						uni-data-checkbox 数据选择器
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="数据驱动的picker选择器">
					<view class="goto-page" @click="myNavigator('/expand/dataPicker')">
						uni-data-picker 数据驱动的picker选择器
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="日期选择器">
					<view class="goto-page" @click="myNavigator('/expand/datetimePicker')">
						uni-datetime-picker 日期选择器
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="抽屉">
					<view class="goto-page" @click="myNavigator('/expand/drawer')">
						uni-drawer 抽屉
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="增强输入框">
					<view class="goto-page" @click="myNavigator('/expand/easyInput')">
						uni-easyinput 增强输入框
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="悬浮按钮">
					<view class="goto-page" @click="myNavigator('/expand/fab')">
						uni-fab 悬浮按钮
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="收藏按钮">
					<view class="goto-page" @click="myNavigator('/expand/fav')">
						uni-fav 收藏按钮
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="文件选择上传">
					<view class="goto-page" @click="myNavigator('/expand/filePicker')">
						uni-file-picker 文件选择上传
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="表单">
					<view class="goto-page" @click="myNavigator('/expand/forms')">
						uni-forms 表单
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="商品导航">
					<view class="goto-page" @click="myNavigator('/expand/goodsNav')">
						uni-goods-nav 商品导航
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="宫格">
					<view class="goto-page" @click="myNavigator('/expand/grid')">
						uni-grid 宫格
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="分组">
					<view class="goto-page" @click="myNavigator('/expand/group')">
						uni-group 分组
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="图标">
					<view class="goto-page" @click="myNavigator('/expand/icons')">
						uni-icons 图标
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="索引列表">
					<view class="goto-page" @click="myNavigator('/expand/indexedList')">
						uni-indexed-list 索引列表
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="列表">
					<view class="goto-page" @click="myNavigator('/expand/list')">
						20.uni-list 列表
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="加载更多">
					<view class="goto-page" @click="myNavigator('/expand/loadMore')">
						uni-load-more 加载更多
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="自定义导航栏">
					<view class="goto-page" @click="myNavigator('/expand/navBar')">
						uni-nav-bar 自定义导航栏
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="通告栏">
					<view class="goto-page" @click="myNavigator('/expand/noticeBar')">
						uni-notice-bar 通告栏
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="数字输入框">
					<view class="goto-page" @click="myNavigator('/expand/numberBox')">
						uni-number-box 数字输入框
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="分页器">
					<view class="goto-page" @click="myNavigator('/expand/pagination')">
						25.uni-pagination 分页器
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="弹出层">
					<view class="goto-page" @click="myNavigator('/expand/popup')">
						uni-popup 弹出层
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="评分">
					<view class="goto-page" @click="myNavigator('/expand/rate')">
						uni-rate 评分
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="搜索栏">
					<view class="goto-page" @click="myNavigator('/expand/searchBar')">
						uni-search-bar 搜索栏
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="分段器">
					<view class="goto-page" @click="myNavigator('/expand/segmentedControl')">
						uni-segmented-control 分段器
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="步骤条">
					<view class="goto-page" @click="myNavigator('/expand/steps')">
						30.uni-steps 步骤条
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="滑动操作">
					<view class="goto-page" @click="myNavigator('/expand/swipeAction')">
						uni-swipe-action 滑动操作
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="轮播图指示点">
					<view class="goto-page" @click="myNavigator('/expand/swiperDot')">
						uni-swiper-dot 轮播图指示点
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="表格">
					<view class="goto-page" @click="myNavigator('/expand/table')">
						uni-table 表格
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="标签">
					<view class="goto-page" @click="myNavigator('/expand/tag')">
						uni-tag 标签
					</view>
				</uni-collapse-item>
			</uni-collapse>
			<uni-collapse class="u-collapse">
				<uni-collapse-item class="first-collapse" title="过渡动画">
					<view class="goto-page" @click="myNavigator('/expand/transition')">
						uni-transition 过渡动画
					</view>
				</uni-collapse-item>
			</uni-collapse>
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
	page {
		background-color: #f7f7f7;
	}

	.whole-page {
		display: flex;
		flex-direction: column;
		flex: 1;
	}
	
	.container {
		display: flex;
		flex: 2;
		justify-content: center;
		align-items: center;
		flex-direction: column;
	}

	.u-section {
		width: 100%;
	}

	.top-image {
		width: 150rpx;
		height: 150rpx;
	}

	.main-container {
		padding: 20rpx;
		display: flex;
		flex-direction: column;
		flex: 8;
	}

	.u-collapse {
		margin: 15rpx 0;
	}

	.goto-page {
		height: 40rpx;
		padding: 10rpx 40rpx;
	}

	.first-collapse {
		background-color: #FFFFFF;
	}
</style>
