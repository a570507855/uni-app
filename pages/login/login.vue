<template>
	<view >
		<view class="status_bar"></view>
		<uni-nav-bar title="登录" leftIcon="back" backgroundColor="skyblue" @clickLeft="clickLeft"></uni-nav-bar>
		<view class="login">
			<view  class="login-item">
				<uni-icons type="person" class="login-item-icon"></uni-icons>
				<input type="text" placeholder="账号"  v-model="form.account" require></label>
				
			</view>
			<view class="login-item">
				<uni-icons type="locked" class="login-item-icon"></uni-icons>
				<input type="text" password="true" placeholder="密码" v-model="form.password">
			</view>
			<view>
				<button type="primary" @click="clickLogin">登录</button>
			</view>
		</view>
		
		
	</view>
</template>

<script>
	import Uicon from '../../components/uni-icons/icons.js'
	export default {
		data() {
			return {
				form:{
					account:'',
					password:''
				}
			}
		},
		methods: {
			clickLeft(){
				uni.navigateBack({})
			},
			clickLogin(){
				console.log(this.form);
	
			}
		},
		components:{
			Uicon
		}
	}
</script>

<style>
	.status_bar{
		height: var(--status-bar-height);
		width: 100%;
		background-color: black;
	}
	.login{
		box-sizing: border-box;
		height: 200px;
		margin: 20px;
		padding: 20px;
	
	}
	.login-item{
		display: flex;
		background-color: #FFFFFF;
		margin: 26rpx 0;
		height: 72rpx;
		line-height: 72rpx;
		border-radius: 5px;
	}
	.login-item input{
		height: inherit;
		line-height: 72rpx;
	}
	.login-item-icon{
		padding: 0 15rpx;
	}
</style>
