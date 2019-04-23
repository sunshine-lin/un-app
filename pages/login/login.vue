<template>
	<view>
		<form @submit="formSubmit" @reset="formReset">
			<view class="section">
				<view class="section__title">账号</view>
				<view class="flex-center-center" style="height: 100upx;padding:0 30upx;">
					<text class="iconfont icon_huiyuanguanli" style="font-size: 35upx;"></text>
					<input name="input" placeholder="请输入账号" style="flex:1;margin-left: 50upx;"/>
				</view>
			</view>
			<view class="section">
				<view class="section__title">密码</view>
				<view class="flex-center-center" style="height: 100upx;padding:0 30upx;">
					<text v-model="ruleForm.username"
					 class="iconfont iconai-password" style="font-size: 35upx;"></text>
					<input v-model="ruleForm.password"
					:password="password"
					name="input" placeholder="请输入密码" style="flex:1;margin-left: 50upx;"/>
					<text class="iconfont iconsee" style="font-size: 40upx;" 
					:style="!password?'color:#4492eb;': 'color: #333;'"
					@tap="password = !password"></text>
				</view>
				
			</view>
			<view class="section section_gap">
				<view class="section__title">记住密码</view>
				<switch name="switch" />
			</view>
			<view class="btn-area">
				<button type="primary">登录</button>
			</view>
		</form>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				password: true,
				ruleForm: {
					username: '',
					password: ''
				}
			};
		}
	}
</script>

<style lang="scss">
	.inputBox{
		display: flex;
		justify-content: space-between;
	}
	.btn-area button{
		background: $uni-color-primary;
	}
</style>
