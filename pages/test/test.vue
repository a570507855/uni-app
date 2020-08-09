<template>
	<view>
		<view class="status_bar"></view>
		<uni-nav-bar title="测试页面" backgroundColor="skyblue" rightText="菜单"></uni-nav-bar>
		<view>
			<text class="title" space="emsp">字体标签 text演示</text>
		</view>
		<text selectable="true" space="emsp">text test</text>
		<view>
			<text >&gt;</text>
			<text decode="false">&gt;</text>
		</view>
		<view class="box" hover-class="box2" hover-start-time="300" hover-stay-time="200">显示效果</view>
		<view>
			<text class="title" space="emsp">字体图标 icon演示</text>
			<icon type="success"></icon>
			<icon type="info"></icon>
			<icon type="warn"></icon>
			<icon type="cancel" color="red" size="30"></icon>
			<icon type="search"></icon>
			<icon type="clear"></icon>
			<icon type="download"></icon>
			<icon type="waiting"></icon>
			<icon type="success-no-circle"></icon>
		</view>
		
		<view>
			<text class="title" space="emsp">富文本 rich-text演示</text>
			<rich-text :nodes="nodes"></rich-text>
		</view>
		
		<view>
			<text class="title" space="emsp">进度条 process演示</text>
			<progress  :percent="percent" show-info stroke-width="3"></progress>
		</view>
		<text class="title" space="emsp">弹出窗 popup演示</text>
		<view style="display: flex;">
			
			<button type="primary" @click="$refs.popup.open()">顶部弹出</button>
			<button type="primary" @click="$refs.popup2.open()">中间弹出</button>
			<button type="primary" @click="$refs.popup3.open()">底部弹出</button>
			<uni-popup ref="popup" type="top">顶部弹出</uni-popup>
			<uni-popup ref="popup2" type="center">中间弹出</uni-popup>
			<uni-popup ref="popup3" type="bottom">底部弹出</uni-popup>
		</view>
		<view>
			<button type="default" @click="$refs.message.open()">弹出消息</button>
			
		<uni-popup ref="message" type="message">
			<uni-popup-message type="error" message="错误提示" :duration="2000"></uni-popup-message>
		</uni-popup>
		<uni-popup ref="dialog" type="dialog">
			<uni-popup-dialog type="success" title="标题" content="内容" ></uni-popup-dialog>
		</uni-popup>
		</view>
	
	</view>
</template>

<script>
	import uniPopup from '@/components/uni-popup/uni-popup.vue'
	import uniPopupMessage from '@/components/uni-popup/uni-popup-message.vue'
	import uniPopupDialog from '@/components/uni-popup/uni-popup-dialog.vue'
	export default {
		data() {
			return {
				percent:20,
				nodes:[{
					type:'node',
					name:'h1',
					attrs:{
						style:'color:red;font-size:30px;font-weight:700;',
					},
					children:[
						{type:'text',text:'rich-text'}
					]
				}]
			}
		},
		methods: {
			
		},
		components:{
			uniPopup,
			uniPopupMessage,
			uniPopupDialog
		}
	}
</script>

<style>
	.status_bar{
		height: var(--status-bar-height);
		width: 100%;
		background-color: #007AFF;
	}
	
	.title{
		display: block;
		font-size: 24px;
		font-weight: 700;
		margin: 20px 0;
	}
	.box{
		width: 80%;
		height: 50px;
		background-color: #4CD964;
		margin: 0 auto;
	}
	.box2{
		background-color: skyblue;
	}
</style>
