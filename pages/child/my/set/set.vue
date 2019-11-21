<template>
	<view>
		<view class="list_group">
			<view class="new_mes">
				<text>新消息提醒</text>
				<text class="uni-icon uni-icon-arrowright"></text>
			</view>
			<view class="new_mes">
				<text>账号管理</text>
				<text class="uni-icon uni-icon-arrowright"></text>
			</view>
			<view class="new_mes">
				<text>字体大小</text>
				<text class="uni-icon uni-icon-arrowright"></text>
			</view>
			<view class="new_mes">
				<text>清除缓存</text>
				<text class="uni-icon uni-icon-arrowright"></text>
			</view>
		</view>
		<view class="list_group">
			<view class="new_mes">
				<text>版本功能介绍</text>
				<text class="uni-icon uni-icon-arrowright"></text>
			</view>
			<view class="new_mes">
				<text>关于我们</text>
				<text class="uni-icon uni-icon-arrowright"></text>
			</view>
			<view class="new_mes">
				<text>检测版本</text>
				<text class="uni-icon uni-icon-arrowright"></text>
			</view>
		</view>
		<view class="quit">
			<text>退出登录</text>
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
	page{
		background: #D9D9D9;
	}
	.list_group{
		display: flex;
		flex-direction: column;
		background: #FFFFFF;
		margin-top:30upx;
	}
	.list_group .new_mes{
		width:100%;height:80upx;
		display: flex;
		justify-content: space-between;
		flex-direction: row;
		align-items: center;
		padding:50upx 40upx;
		line-height: 80upx;
		border-bottom:2upx solid #E5E5E5;
	}
	.quit{
		width:100%;height:80upx;
		line-height: 80upx;
		text-align: center;
		background: #FFFFFF;
		margin-top:30upx;
	}
</style>
