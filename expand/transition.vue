<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
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
				cpntitle: 'uni-transition 过渡动画',
				cpnDescrbe: "元素的简单过渡动画",
				cpnName: "uni-transition",
				number: 9.1,
				show: false,
				modeClass: ['fade'],
				showS:true
			}
		},
		components: {
			cpninfo
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

	.title{
		width: 100%;
		font-size: 50rpx;
		font-weight: bold;
		background-color: #6fdbdd;
		display: flex;
		justify-content: center;
		align-items: flex-start;
	}


	.active {
		width: 100%;
		height: 200rpx;
		display: flex;
		justify-content: center;
		align-items: center;
	}
</style>
