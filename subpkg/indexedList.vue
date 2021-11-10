<template>
	<view class="container">
		<view class="container-top">
			<view class="title">
				uni-indexed-list 索引列表
			</view>
			<view class="description">
				索引列表组件，右侧带索引的列表，方便快速定位到具体内容，通常用于城市/机场选择等场景
			</view>
			<view class="author">
				<view class="author-detail">
					作者： DCloud前端团队
				</view>
				<image class="logo-image" src="/static/logo.png"></image>
			</view>
			插件ID：uni-indexed-list <br>
			插件包体积：6.3KB
			<view class="git-info">
				<image class="git-image" src="/static/git.png"></image>
				<uni-link href="https://github.com/dcloudio/uni-ui" text="https://github.com/dcloudio/uni-ui">
				</uni-link>
			</view>
		</view>
		<view class="container-bottom-view">
			<view class="title">
				概述
			</view>
			<view class="index-view">
				<uni-indexed-list class="uni-indexed-list" :options="list" :showSelect="true"></uni-indexed-list>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [{
						letter: 'A',
						data: ['阿克苏机场', '阿拉山口机场']
					},
					{
						letter: 'B',
						data: ['保山机场', '包头机场']
					},
					{
						letter: 'C',
						data: ['长白山机场', '长春龙嘉国际机场']
					},
					{
						letter: 'D',
						data: ['大理机场', '大连周水子国际机场']
					},
					{
						letter: 'E',
						data: ['鄂尔多斯机场', '恩施许家坪机场']
					},
					{
						letter: 'F',
						data: ['阜阳西关机场', '福州长乐国际机场']
					},
					{
						letter: 'G',
						data: ['赣州黄金机场', '格尔木机场']
					},
					{
						letter: 'H',
						data: ['哈尔滨太平国际机场', '哈密机场']
					},
					{
						letter: 'I',
						data: []
					},
					{
						letter: 'J',
						data: ['济南遥墙国际机场', '济宁曲阜机场']
					},
					{
						letter: 'K',
						data: ['喀什机场', '克拉玛依机场']
					},
					{
						letter: 'L',
						data: ['拉萨贡嘎机场', '兰州中川机场']
					},
					{
						letter: 'M',
						data: ['满洲里西郊机场', '绵阳南郊机场']
					},
					{
						letter: 'N',
						data: ['南昌昌北国际机场', '南充高坪机场']
					},
					{
						letter: 'O',
						data: []
					},
					{
						letter: 'P',
						data: ['普洱思茅机场']
					},
					{
						letter: 'Q',
						data: ['齐齐哈尔三家子机场', '秦皇岛山海关机场']
					},
					{
						letter: 'R',
						data: ['日喀则和平机场']
					},
					{
						letter: 'S',
						data: ['三亚凤凰国际机场', '汕头外砂机场']
					},
					{
						letter: 'T',
						data: ['塔城机场', '太原武宿国际机场']
					},
					{
						letter: 'U',
						data: []
					},
					{
						letter: 'V',
						data: []
					},
					{
						letter: 'W',
						data: ['万州五桥机场', '潍坊机场']
					},
					{
						letter: 'X',
						data: ['西安咸阳国际机场', '西昌青山机场']
					},
					{
						letter: 'Y',
						data: ['延安二十里堡机场', '盐城机场']
					},
					{
						letter: 'Z',
						data: ['湛江机场', '昭通机场']
					}
				]
			}
		},
		methods: {}
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
		height: 300rpx;
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

	.uni-indexed-list {
		position: absolute;
		left: 0;
		top: 415rpx;
		right: 0;
		bottom: 0;
		/* padding-bottom: 20rpx; */
	}
</style>
