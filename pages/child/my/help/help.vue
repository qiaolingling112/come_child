<template>
	<view>
		<view class="question">
			<view v-for="(item,index) in meslist" :key="index">{{item.title}}</view>
		</view>
		<view class="uni-tab-bar">
			<view class="left" @tap="getmes">
				<text class="uni-icon uni-icon-compose"></text>
				<text>意见反馈</text>
			</view>
			<view class="right" @tap="inline">
				<text class="uni-icon uni-icon-chatboxes"></text>
				<text>在线咨询</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				meslist:[
					{title:'如何修改宝宝信息?'},
					{title:'如何修改绑定手机号?'},
					{title:'如何修改密码?'},
					{title:'如何修改宝宝信息?'},
					{title:'如何修改绑定手机号?'},
					{title:'如何修改密码?'}
				]
			}
		},
		methods: {
			getmes:function(){
				uni.showToast({
					title:'意见反馈',
					icon:'none'
				})
			},
			inline:function(){
				uni.showToast({
					title:'在线咨询',
					icon:'none'
				})
			}
		}
	}
</script>

<style>
	.question{
		width:100%;height:600upx;
		display: flex;
		justify-content: center;
		flex-direction: row;
		flex-wrap: wrap;
		align-items: center;
		padding-top:40upx;
	}
	.question view{
		width:48%;height:160upx;
		line-height:160upx;
		text-align: center;
		padding:20upx;
		border: 2upx solid #E5E5E5;
	}
	.uni-tab-bar{
		width:100%;height:160upx;
		position: fixed;
		bottom:0;left:0;right:0;
		border-top:2upx solid #E5E5E5;
		display: flex;
		justify-content: center;
		flex-direction: row;
		align-items: center;
		padding:20upx;
	}
	.uni-tab-bar view{
		width:50%;height:120upx;
		line-height:100upx;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.uni-tab-bar .left{
		border-right:2upx solid #E5E5E5;
	}
</style>
