<template>
	<view>
		<view class="toux">
			<view class="left">
				<image src="../../../static/gotoScrol.jpg" mode="aspectFill"></image>
			</view>
			<view class="right">
				<text class="name">李雷小朋友</text>
				<text>我已经5岁10月25天了</text>
			</view>
		</view>
		<view class="list">
			<view class="help">
				<text class="uni-icon uni-icon-help"></text>
				<text class="help_center">帮助中心</text>
				<navigator url="help/help"><text class="uni-icon uni-icon-arrowright"></text></navigator>
			</view>
			<view class="help">
				<text class="uni-icon uni-icon-search"></text>
				<text class="help_center">审核进度查询</text>
				<navigator url="search/search"><text class="uni-icon uni-icon-arrowright"></text></navigator>
			</view>
			<view class="help">
				<text class="uni-icon uni-icon-chat"></text>
				<text class="help_center">我的动态</text>
				<navigator url="my_active/my_active"><text class="uni-icon uni-icon-arrowright"></text></navigator>
			</view>
			<view class="help">
				<text class="uni-icon uni-icon-settings"></text>
				<text class="help_center">设置</text>
				<navigator url="set/set"><text class="uni-icon uni-icon-arrowright"></text></navigator>
				
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
		methods: {
			
		}
	}
</script>

<style>
	.toux{
		width:100%;height:180upx;
		padding-top:20upx;
		display: flex;
		flex-direction: row;
		align-items: flex-start;
		padding-left:20upx;
	}
	.toux .left{
		width:160upx;height:160upx;
	}
	.toux .left image{
		width:100%;height:100%;
		border-radius: 50%;
	}
	.toux .right{
		width:320upx;height:160upx;
		display: flex;
		justify-content: center;
		flex-direction: column;
		align-items:flex-start;
		padding-left:20upx;
	}
	.list{
		width:100%;
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		margin-top:40upx;
		border-top:2upx solid #E5E5E5 ;
		padding-left:26upx;
	}
	.list view{
		width:100%;hegiht:60upx;
		padding-top:26upx;
		padding-bottom:26upx ;
		border-bottom: 2upx solid #E5E5E5;
	}
	.help_center{
		display: inline-block;
		width:320upx;height:80upx;
		line-height:80upx;
		font-size: 28upx;
	}
	.list view .uni-icon-help,.uni-icon-search,.uni-icon-chat,.uni-icon-settings{
		display: inline-block;
		width:80upx;height:80upx;
		line-height: 80upx;
		text-align: center;
		font-size: 50upx;
		color:#E80080;
		padding-right:80upx;
	}
	.list view .uni-icon-search{
		color:#09BB07;
	}
	.list view .uni-icon-chat{
		color:#8A6DE9;
	}
	.list view .uni-icon-settings{
		color:#F0AD4E;
	}
	.list view navigator{
		display: inline-block;
		width:270upx;height:80upx;
		text-align: right;
	}
	.list view .uni-icon-arrowright{
		font-size: 50upx;
		line-height: 80upx;
	}
</style>
