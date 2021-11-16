<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
		<view class="container-bottom">
			<view class="title">
				概述
			</view>
			<uni-easyinput :type="typeStyle" :placeholderStyle="placeholderstyle" :clearable="clearAble"
				:disabled="disAble" :suffixIcon="sufFixIcon" :prefixIcon="preFixIcon" v-model="value"
				placeholder="请输入内容" focus>
			</uni-easyinput>
			<uni-section title="改变样式" type="line"></uni-section>
			<view class="change-style">
				<button class="change-to-area" @click="changeArea">多行文本</button>
				<button class="change-to-pass" @click="changePass">密码文本</button>
				<!-- <button class="change-to-num" @click="changeNum">数字输入</button>
				<button class="change-to-id" @click="changeId">身份证输入</button>
				<button class="change-to-digit" @click="changeDigit">带小数点</button> -->
				<button class="change-to-text" @click="changeText">文本输入框</button>
			</view>
			<uni-section title="显示/隐藏查找图标" type="line"></uni-section>
			<view class="show-inco">
				<button class="show-inco-pre" @click="ShadowPre">显示/隐藏在前方</button>
				<button class="show-inco-suf" @click="ShadowSuf">显示/隐藏在后方</button>
			</view>
			<uni-section title="只读与更改" type="line"></uni-section>
			<view class="read-only">
				<button class="read-only" @click="readyOnly">只读/填写</button>
			</view>
			<uni-section title="显示/隐藏(有文字后有效)" type="line"></uni-section>
			<view class="clear-able">
				<button class="clear-able" @click="clearSable">显示/隐藏清除按钮</button>
			</view>
			<uni-section title="改变placeholder颜色" type="line"></uni-section>
			<view class="change-color">
				<button class="change-color" @click="changeColor">改变颜色</button>
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
				cpntitle: 'uni-easyinput 增强输入框',
				cpnDescrbe: "Easyinput 组件是对原生input组件的增强",
				cpnName: "uni-easyinput",
				number: 9.1,
				preFixIcon: "",
				sufFixIcon: "",
				disAble: false,
				clearAble: true,
				placeholderstyle: "color: #ddd",
				typeStyle: "text"
			}
		},
		components: {
			cpninfo
		},
		methods: {
			changeArea() {
				this.typeStyle = "textarea"
			},
			changePass(){
				this.typeStyle = "password"
			},
			// changeNum(){
			// 	this.typeStyle = "number"
			// },
			// changeId(){
			// 	this.typeStyle = "idcard"
			// },
			// changeDigit(){
			// 	this.typeStyle = "digit"
			// },
			changeText(){
				this.typeStyle = "text"
			},
			ShadowPre() {
				if (this.preFixIcon === "") {
					this.preFixIcon = "search"
				} else {
					this.preFixIcon = ""
				}
			},
			ShadowSuf() {
				if (this.sufFixIcon === "") {
					this.sufFixIcon = "search"
				} else {
					this.sufFixIcon = ""
				}
			},
			readyOnly() {
				this.disAble = !this.disAble
			},
			clearSable() {
				this.clearAble = !this.clearAble
			},
			changeColor() {
				const rgb = []
				for (let i = 0; i < 3; ++i) {
					let color = Math.floor(Math.random() * 256).toString(16)
					color = color.length == 1 ? '0' + color : color
					rgb.push(color)
				}
				this.placeholderstyle = 'color:#' + rgb.join('')
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
	
	.change-style{
		display: flex;
		flex-direction: row;
	}

	.show-inco {
		display: flex;
		flex-direction: row;
	}

	.power {
		display: flex;
		flex-direction: row;
	}
</style>
