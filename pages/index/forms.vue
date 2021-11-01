<template>
	<view class="container">
		<view class="container-top">
			<view class="title">
				uni-forms 表单
			</view>
			<view class="description">
				由输入框、选择器、单选框、多选框等控件组成，用以收集、校验、提交数据
			</view>
			<view class="author">
				<view class="author-detail">
					作者： DCloud前端团队
				</view>
				<image class="logo-image" src="/static/logo.png"></image>
			</view>
			插件ID：uni-forms <br>
			插件包体积：22.2KB
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
	export default {
		data() {
			return {
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

	.input {
		
	}
</style>
