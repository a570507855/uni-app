<template>
	<view>
		<view class="status_bar"></view>
		<uni-nav-bar title="个人中心" backgroundColor="skyblue" :rightText="rightText" @clickRight="clickRight"></uni-nav-bar>
		<view class="head-sculpture">
			<view class="head-img">
				<img :src="headImg" alt="">
			</view>
		</view>
		<view>
			<uni-list>
				<uni-list-item title="我的信息" showExtraIcon="true" :extraIcon="{type:'person',size:'25',color:'skyblue'}"></uni-list-item>
				<uni-list-item title="收藏" showExtraIcon="true" :extraIcon="{type:'heart',size:'25',color:'skyblue'}"></uni-list-item>
				<uni-list-item title="设置" showExtraIcon="true" :extraIcon="{type:'gear',size:'25',color:'skyblue'}"></uni-list-item>
			</uni-list>
			
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				rightText:'登录',
				headImg:'static/img/head.jpg'
			}
		},
		methods: {
			clickRight(){
				uni.navigateTo({
					url:'../login/login'
				})
			}
		}
	}
</script>

<style>
	.status_bar{
		height: var(--status-bar-height);
		width: 100%;
		background-color: black;
	}
	.head-sculpture{
		/* border: 1px solid #007AFF; */
		height: 300rpx;
		display: flex;
		justify-content: center;
		align-items: center;
	}
	.head-img{
		background-color: #FFFFFF;
		width: 150rpx;
		height: 150rpx;
		border-radius: 75rpx;
	}
	.head-img img{
		width: 100%;
		border-radius: inherit
	}
</style>
