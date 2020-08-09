<template>
	<view class="index">
		<view class="status_bar"> <!-- 这里是状态栏 --></view>
		<uni-nav-bar  right-text="注册" title="登录" backgroundColor="skyblue" @clickRight="clickRight"></uni-nav-bar>
		<view>
			<form action="http://localhost:9999//login" methods="post" @submit="formSubmit" @reset="formReset">
				<view class="uni-form-item">
					<label>账号</label>
					<input class="uni-input" type="number" name="account" placeholder="输入框"/>
				</view>
				<view class="uni-form-item">
					<label>密码</label>
					<input class="uni-input"  password="true" name="password" placeholder="输入框"/>
				</view>
				<view>
					<button form-type="submit">提交</button>
				</view>
			</form>
		</view>
		<uni-popup ref="popup" type="message">底部弹出 Popup</uni-popup>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				href: 'https://uniapp.dcloud.io/component/README?id=uniui',
				percent:10
			}
		},
		methods: {
			formSubmit(e){
				console.log('提交')
				var formdata = e.detail.value
				console.log(formdata);
				uni.request({
					method:"POST",
					url:"http://localhost:9999/login",
					data:formdata,
					header:{
						'content-type':'application/x-www-form-urlencoded'
					}
				})
			},
			formReset(){
				console.log('重置')
			},
			clickRight(){
				console.log(122)
				this.$refs.popup.open();
			}
		},
		onLaunch: function() {
			console.log('index Launch');
		},
		onShow: function() {
			console.log('index Show');
		},
		onHide: function() {
			console.log('index Hide');
		}
	}
</script>

<style>

	.uni-input{
		background-color: #FFFFFF;
	}
	
	.status_bar {
	    height: var(--status-bar-height);
	    width: 100%;
		background-color: #007AFF;
	}
		  
</style>
