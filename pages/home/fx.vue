<template>
	<view class="content">
		<view>
			<text class="title">{{title}}</text>
		</view>
	</view>
</template>

<script>
	export default {
		onPullDownRefresh() {
        console.log("开始刷新");
        uni.showLoading({
            title: '加载中...'
        });//出现加载中图标
        this.fresh();//重点在这里，执行你需要执行的动作，和下面methods中一致
        setTimeout(function(){
            console.log("关闭刷新");
            uni.stopPullDownRefresh();//关闭刷新，不关闭会一直刷新不加载内容
        },1000)//1s后关闭刷新
        },
		data() {        onPullDownRefresh() {
        console.log("开始刷新")
        uni.showLoading({
            title: '加载中...'
        })//出现加载中图标
        this.fresh();//重点在这里，执行你需要执行的动作，和下面methods中一致
        setTimeout(function(){
            console.log("关闭刷新");
            uni.stopPullDownRefresh();//关闭刷新，不关闭会一直刷新不加载内容
        },1000)//1s后关闭刷新
        }
			return {
				title: 'Hello'
			}
		},

		methods: {
           fresh: function(){
            uni.request({
                url: 'https://unidemo.dcloud.net.cn/api/news',
                method: 'GET',
                data: {},
                success: res => {
                    this.news = res.data;
                    uni.hideLoading();//关闭加载中图标
                    console.log("获取数据完成");
                },
                fail: () => {},
                complete: () => {}
            })
        }
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
