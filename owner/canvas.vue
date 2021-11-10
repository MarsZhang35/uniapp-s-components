<template>
	<view class="container">
		<view class="title">
			canvas 画布
		</view>
	<canvas class="first-canvas" style="width: 300px; height: 200px;" canvas-id="firstCanvas" id="firstCanvas"></canvas>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		onReady: function(e) {
			var context = uni.createCanvasContext('firstCanvas')
			context.setStrokeStyle("#00ff00")
			context.setLineWidth(5)
			context.rect(0, 0, 200, 200)
			context.stroke()
			context.setStrokeStyle("#ff0000")
			context.setLineWidth(2)
			context.moveTo(160, 100)
			context.arc(100, 100, 60, 0, 2 * Math.PI, true)
			context.moveTo(140, 100)
			context.arc(100, 100, 40, 0, Math.PI, false)
			context.moveTo(85, 80)
			context.arc(80, 80, 5, 0, 2 * Math.PI, true)
			context.moveTo(125, 80)
			context.arc(120, 80, 5, 0, 2 * Math.PI, true)
			context.stroke()
			context.draw()
		},
		methods: {

		}
	}
</script>

<style>
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
</style>
