<template>
	<view class="content">
		<input type="text" focus v-model="username" placeholder="请输入用户名"></input>
		<view>
			<input type="password"  v-model="password" placeholder="请输入密码"></input>
		<!-- 	<uni-icon type="eye" size="20" @click='flagEye'></uni-icon> -->
		</view>
		<button type="primary" @click="login">登录</button>
	</view>
</template>

<script>
	import uniIcon from "@dcloudio/uni-ui/lib/uni-icon/uni-icon.vue"
	export default {
		components: {
			uniIcon
		},
		data() {
			return {
				username: "lhx",
				password: "123456",
				flag: true
			}
		},
		methods: {
/* 			flagEye() {
				this.flag=!this.flag;
			}, */
			login() {

					uni.navigateTo({
					url: '../home/index'
				});
	
			}
		},
		onNavigationBarButtonTap() {
			uni.navigateTo({
				url: 'register'
			});
		}
	}
</script>

<style>
	@import url("../../static/css/login.css");
</style>
