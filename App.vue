<script>
export default {
	onLaunch: function() {
		console.log('App Launch');
	},
	onShow: function() {
		console.log('App Show');
	},
	onHide: function() {
		console.log('App Hide');
	}
};
</script>

<style>
/* 解决头条小程序组件内引入字体不生效的问题 */
/* #ifdef MP-TOUTIAO */
@font-face {
	font-family: uniicons;
	src: url('/static/uni.ttf');
}
/* #endif */
	.pages-login-login{
/* 		background-image: url(static/img/bg2.jpg);
		background-repeat: no-repeat;
		background-size: cover; */
		background-image: linear-gradient(180deg,skyblue 20%,white);
	}

</style>
