<template>
	<view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		},
		onLoad() {
			uni.login({
				provider:'weixin',
				success(info) {
					console.log(info);
				}
			})
		}
	}
</script>

<style>

</style>
