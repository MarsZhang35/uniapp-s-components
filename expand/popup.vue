<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
		<view class="container-bottom-view">
			<view class="title">
				概述
			</view>
			<uni-section title="弹出方位" type="line"></uni-section>
			<view class="show">
				<button @click="openT">顶部</button>
				<uni-popup ref="popup" type="top">Popup内容</uni-popup>
				<button @click="openB">底部</button>
				<uni-popup ref="popup" type="bottom">Popup内容</uni-popup>
				<button @click="openM">中间</button>
				<uni-popup ref="popup" type="center">Popup内容</uni-popup>
				<button @click="openL">左侧</button>
				<uni-popup ref="popup" type="left">Popup内容</uni-popup>
				<button @click="openR">右侧</button>
				<uni-popup ref="popup" type="right">Popup内容</uni-popup>
			</view>
			<uni-section title="各种显示" type="line"></uni-section>
			<button style="background-color: #4cd964;" @click="toggleMessage('success')">成功</button>
			<button style="background-color: #dd524d;" @click="toggleMessage('error')">错误</button>
			<button style="background-color: #f0ad4e;" @click="toggleMessage('warn')">警告</button>
			<button style="background-color: #909399;" @click="toggleMessage('info')">信息</button>
			<!-- 消息提示 -->
			<uni-popup ref="popupMessage" type="message">
				<uni-popup-message :type="msgType" :message="message" :duration="700" />
			</uni-popup>
			<!-- 对话框 -->
			<uni-popup ref="popupDialog" type="dialog">
				<uni-popup-dialog :type="msgType" title="通知" content="欢迎使用 uni-popup!" :before-close="true"
					@confirm="dialogConfirm" @close="dialogClose" />
			</uni-popup>
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
				cpntitle: 'uni-popup 弹出层',
				cpnDescrbe: "Popup 组件，提供常用的弹层",
				cpnName: "uni-popup",
				number: 16.1,
				msgType: 'success',
				message: '这是一条成功消息提示'
			}
		},
		components: {
			cpninfo
		},
		methods: {
			openT() {
				this.$refs.popup.open('top')
			},
			openB() {
				this.$refs.popup.open('bottom')
			},
			openM() {
				this.$refs.popup.open('center')
			},
			openL() {
				this.$refs.popup.open('left')
			},
			openR() {
				this.$refs.popup.open('right')
			},
			toggleMessage(type) {
				this.msgType = type;
				switch (type) {
					case 'success':
						this.message = '这是一条成功消息提示';
						break;
					case 'warn':
						this.message = '这是一条警告消息提示';
						break;
					case 'info':
						this.message = '这是一条消息提示';
						break;
					case 'error':
						this.message = '这是一条错误消息提示';
						break;
				}
				this.$refs['popupDialog'].open();
			},
			dialogConfirm() {
				this.$refs.popupMessage.open();

				this.$refs['popupDialog'].close();
			},
			dialogClose() {
				this.msgType = 'info';
				this.message = '点击了对话框的取消按钮';
				this.$refs.popupMessage.open();

				this.$refs.popupDialog.close();
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

	.show {
		display: flex;
		flex-direction: row;
	}
</style>
