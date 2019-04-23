<template>
	<view class="content">
		<image class="logo" src="../../static/logo.png"></image>
		<view>
			<text class="title">{{title}}</text>
		</view>
		<!-- 	  <button @tap="btnTab">跳转1</button> -->
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

		}
	}
</script>

<style>
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
