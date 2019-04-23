<template>
	<view id="index" class="content">
		<image class="logo" src="../../static/logo.png"></image>
		<view>
			<text class="title">{{title}}</text>
		</view>
		<button type="primary" @tap="btnClick('login')">登录</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello uniapp in android'
			}
		},
		onLoad() {
			console.log(uni.getSystemInfoSync().platform)
		},
		methods: {
			btnClick(from) {
				switch (from) {
					case 'login':
						uni.navigateTo({
							url: '/pages/login/login',
							success: res => {},
							fail: () => {},
							complete: () => {}
						});
						break;
				}
			}
		}
	}
</script>

<style>
	#index {}

	.content {
		text-align: center;
		height: 400upx;
	}

	.logo {
		height: 200upx;
		width: 200upx;
		margin-top: 200upx;
	}

	.title {
		font-size: 36upx;
		color: #8f8f94;
	}
</style>
