<template>
	<view class="container">
		<cpninfo :cpntitle="cpntitle" :cpnDescrbe="cpnDescrbe" :cpnName="cpnName" :number="number">
		</cpninfo>
		<view class="container-bottom-view">
			<view class="title">
				概述
			</view>
			<view>
				<uni-forms ref="form" :modelValue="formData" :rules="rules">
					<uni-forms-item label="姓名" name="name">
						<uni-easyinput type="text" v-model="formData.name" placeholder="请输入姓名" />
					</uni-forms-item>
					<uni-forms-item label="邮箱" name="email">
						<uni-easyinput type="text" v-model="formData.email" placeholder="请输入邮箱" />
					</uni-forms-item>
				</uni-forms>
				<button @click="submit">Submit</button>
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
				cpntitle: 'uni-forms 表单',
				cpnDescrbe: "由输入框、选择器、单选框、多选框等控件组成，用以收集、校验、提交数据",
				cpnName: "uni-forms",
				number: 22.2,
				formData: {
					name: '',
					email: ''
				},
				rules: {
					// 对name字段进行必填验证
					name: {
						rules: [{
								required: true,
								errorMessage: '请输入姓名',
							},
							{
								minLength: 2,
								maxLength: 5,
								errorMessage: '姓名长度在 {minLength} 到 {maxLength} 个字符',
							}
						]
					},
					// 对email字段进行必填验证
					email: {
						rules: [{
							format: 'email',
							errorMessage: '请输入正确的邮箱地址',
						}]
					}
				}
			}
		},
		components: {
			cpninfo
		},
		methods: {
			submit() {
				this.$refs.form.validate().then(res => {
					console.log('表单数据信息：', res);
				}).catch(err => {
					console.log('表单错误信息：', err);
				})
			},

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
		margin-bottom: 10rpx;
	}
</style>
