<template>
	<view>
		<view class="header">
			<view class="bg">
				<view class="box">
					<view class="box-hd">
						<view class="avator">
							<img src="../../static/img/face.jpg">
						</view>
						<view class="phone-number">1123996281</view>
					</view>
					<view class="box-bd">
						<view class="item">
							<view class="icon"><img src="../../static/img/message.png"></view>
							<view class="text">我的通知</view>
						</view>
						<view class="item">
							<view class="icon"><img src="../../static/img/favorite.png"></view>
							<view class="text">我的收藏</view>
						</view>
						<view class="item">
							<view class="icon"><img src="../../static/img/service.png"></view>
							<view class="text">我的客服</view>
						</view>
					</view>
				</view>
			</view>
		</view>
		<view class="list-content">
			<view class="list">
				<view class="li noborder" @click="ower">
					<view class="icon"><image src="../../static/img/card.png"></image></view>
					<view class="text">我的名片</view>
					<image class="to" src="../../static/img/to.png"></image>
				</view>
			</view>
			<view class="list">
				<view class="li " @click="changeSkin">
					<view class="icon"><image src="../../static/img/skin.png"></image></view>
					<view class="text">主题切换</view>
					<image class="to" src="../../static/img/to.png"></image>
				</view>
				<view class="li " @click="changehelp" >
					<view class="icon"><image src="../../static/img/help.png"></image></view>
					<view class="text">帮助中心</view>
					<image class="to" src="../../static/img/to.png"></image>
				</view>
				<view class="li " >
					<view class="icon"><image src="../../static/img/about.png"></image></view>
					<view class="text">关于我们</view>
					<image class="to" src="../../static/img/to.png"></image>
				</view>
				<view class="li " >
					<view class="icon"><image src="../../static/img/opinion.png"></image></view>
					<view class="text">意见反馈</view>
					<image class="to" src="../../static/img/to.png"></image>
				</view>
				<view class="li " >
					<view class="icon"><image src="../../static/img/about.png"></image></view>
					<view class="text" @click="fn">日常签到</view>
					
					<view>
						<fl-signin 
							:date="date" 
							:list="list" 
							@signin_fun="signin_fun" 
							:repair="repair" 
							:rule="rule" 
							@repair_fun="repair_fun" 
							:choose_date="choose_date" 
							@date_change="date_change"
						></fl-signin>
					</view>
					
					<image class="to" src="../../static/img/to.png"></image>
				</view>
			</view>
			<view class="list"  @click="anquan">
				<view class="li noborder" >
					<view class="icon"><image src="../../static/img/set.png"></image></view>
					<view class="text">安全中心</view>
					<image class="to" src="../../static/img/to.png"></image>
				</view>
			</view>
			<view class="btn">
		      <button type="primary" @click="login">
				退出登录
			  </button>
			</view>
		</view>
	</view>
</template>
<script>
	export default {
		data() {
			   return {
		}
		},
		onLoad() {
		},
		methods: {
			changeSkin(){
				uni.navigateTo({
						url: '../skin-change/skin-change'
				});
			},
			 anquan(){
				uni.navigateTo({
						url: '../skin-change/anquan'
				});
			},
        	ower(){
				uni.navigateTo({
						url: '../skin-change/ower'
				});
			},
			login(){
					uni.navigateTo({
					url: '../home/login'
				});
			},
			fn(){
				uni.navigateTo({
					url: '../skin-change/fl-signin/fl-signin'
			  });
			}
			
		}
	}
</script>

<style lang="scss">
.btn{
	width: 84%;
	margin: 3% 8%;
}
page{
	background-color:#f1f1f1;
	font-size: 30upx;
}
.header{
	background: #fff;
	height: 290upx;
	padding-bottom: 110upx;
	.bg{
		width: 100%;
		height:200upx;
		padding-top:100upx;
		background-color:#4191ea;
	}
}
.box{
	width: 650upx;
	height: 280upx;
	border-radius: 20upx;
	margin: 0 auto;
	background: #fff;
	box-shadow: 0 5upx 20upx 0upx rgba(0, 0, 150, .2); 
	.box-hd{
		display: flex;
		flex-wrap: wrap;
		flex-direction: row;
		justify-content: center;
		.avator{
			width: 160upx;
			height: 160upx;
			background: #fff;
			border: 5upx solid #fff;
			border-radius: 50%;
			margin-top: -80upx;
			overflow: hidden;
			img{
				width: 100%;
				height: 100%;
			}
		}
		.phone-number{
			width: 100%;
			text-align: center;
		}
	}
	.box-bd{
		display: flex;
		flex-wrap: nowrap;
		flex-direction: row;
		justify-content: center;
		.item{
			flex: 1 1 auto;
			display: flex;
			flex-wrap: wrap;
			flex-direction: row;
			justify-content: center;
			border-right: 1px solid #f1f1f1;
			margin: 15upx 0;
			&:last-child{
				border: none;
			}
			.icon{
				width: 60upx;
				height: 60upx;
				img{
					width: 100%;
					height: 100%;
				}
			}
			.text{
				width: 100%;
				text-align: center;
				margin-top: 10upx;
			}
		}
	}
}
.list-content{
	background: #fff;
}
.list{
	width:100%;
	border-bottom:15upx solid  #f1f1f1;
	background: #fff;
	&:last-child{
		border: none;
	}
	.li{
		width:92%;
		height:100upx;
		padding:0 4%;
		border-bottom:1px solid rgb(243,243,243);
		display:flex;
		align-items:center;
	&.noborder{
		border-bottom:0
		}
		.icon{
			flex-shrink:0;
			width:50upx;
			height:50upx;
			image{
				width:50upx;
				height:50upx;
			}
		}
		.text{
			padding-left:20upx;
			width:100%;
			color:#666;
		}
		.to{
			flex-shrink:0;
			width:40upx;
			height:40upx;
		}
	}
}
</style>
