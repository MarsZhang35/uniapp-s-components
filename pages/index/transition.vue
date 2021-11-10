<template>
	<view class="container">
		<view class="container-top">
			<view class="title">
				uni-transition 过渡动画
			</view>
			<view class="description">
				元素的简单过渡动画
			</view>
			<view class="author">
				<view class="author-detail">
					作者： DCloud前端团队
				</view>
				<image class="logo-image" src="/static/logo.png"></image>
			</view>
			插件ID：uni-transition <br>
			插件包体积：9.1KB
			<view class="git-info">
				<image class="git-image" src="/static/git.png"></image>
				<uni-link href="https://github.com/dcloudio/uni-ui" text="https://github.com/dcloudio/uni-ui">
				</uni-link>
			</view>
		</view>
		<view class="container-bottom">
			<view class="title">
				概述
			</view>
			<view>
				<view class="active">
					<uni-transition class="u-transition" :duration="500" :mode-class="modeClass"
						:styles="{'width':'200rpx','height':'200rpx','backgroundColor':'red'}" :show="show">
					</uni-transition>
				</view>
				<uni-section title="动画的显现" type="line"></uni-section>
				<view class="change-shadow-view">
					<button @click="open(['slide-top'])">slide-top</button>
					<button @click="open(['slide-left'])">slide-left</button>
					<button @click="open(['slide-right'])">slide-right</button>
					<button @click="open(['slide-bottom'])">slide-bottom</button>
					<button @click="open(['fade'])">fade</button>
					<button @click="open(['zoom-in', 'fade'])">zoom-in</button>
					<button @click="open(['zoom-out', 'fade'])">zoom-out</button>
				</view>
				<uni-section title="动画的组合显现" type="line"></uni-section>
				<view>
					<button @click="open(['fade','zoom-out','slide-top'])">组合动画示例一</button>
					<button @click="open(['zoom-in','slide-bottom','fade'])">组合动画示例二</button>
					<button @click="open(['slide-left','slide-top','fade'])">组合动画示例三</button>
				</view>
				<view class="active">
					<uni-transition ref="ani" :styles="{'width':'100rpx','height':'100rpx','backgroundColor':'red'}"
						:show="showS"></uni-transition>
				</view>
				<uni-section title="动画开始" type="line"></uni-section>
				<button @click="run">执行动画</button>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				show: false,
				modeClass: ['fade'],
				showS:true
			}
		},
		onShow() {
			//手动配置初始化参数，可以没有
			this.$refs.ani.init({
				duration: 2000,
				timingFunction: 'linear',
				transformOrigin: '50% 50%',
				delay: 500
			})
		},
		methods: {
			open(mode) {
				this.modeClass = mode;
				this.show = !this.show
			},
			run() {
				console.log('执行开始')
				// 同时右平移到 100rpx,旋转 360 读
				this.$refs.ani.step({
					translateX: '100rpx',
					rotate: '360'
				})
				// 上面的动画执行完成后，等待200毫秒平移到 0rpx,旋转到 0
				this.$refs.ani.step({
					translateX: '0rpx',
					rotate: '0'
				}, 
				{
					timingFunction: 'ease-in',
					duration: 200
				})
				// 开始执行动画
				this.$refs.ani.run(() => {
					console.log('动画支持完毕')
				})
				console.log('执行完了')
			}
		}
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


	.active {
		width: 100%;
		height: 200rpx;
		display: flex;
		justify-content: center;
		align-items: center;
	}
</style>
