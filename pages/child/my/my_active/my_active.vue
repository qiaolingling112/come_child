<template>
	<view>
		<view class="top_bg"></view>
		<view class="tab">
			<view class="top">
				<view class="tx_image">
					<image src="../../../../static/gotoScrol.jpg" mode="aspectFill"></image>
				</view>
				<view class="name">
					<text class="blue">李雷宝宝</text>
					<text>今天是李雷宝宝第一天上学，加油！</text>
				</view>
				
			</view>
			<view class="bottom">
				<image src="../../../../static/index_bottom1.jpg" mode="aspectFill"></image>
				<image src="../../../../static/index_bottom2.jpg" mode="aspectFill"></image>
				<image src="../../../../static/index_bottom1.jpg" mode="aspectFill"></image>
			</view>
		</view>
		<view class="tab">
			<view class="top">
				<view class="tx_image">
					<image src="../../../../static/gotoScrol.jpg" mode="aspectFill"></image>
				</view>
				<view class="name">
					<text class="blue">李雷宝宝</text>
					<text>今天是李雷宝宝第一天上学，加油！</text>
				</view>
				
			</view>
			<view class="bottom">
				<image src="../../../../static/index_bottom1.jpg" mode="aspectFill"></image>
				<image src="../../../../static/index_bottom2.jpg" mode="aspectFill"></image>
				<image src="../../../../static/index_bottom1.jpg" mode="aspectFill"></image>
			</view>
		</view>
		<view class="tab">
			<view class="top">
				<view class="tx_image">
					<image src="../../../../static/gotoScrol.jpg" mode="aspectFill"></image>
				</view>
				<view class="name">
					<text class="blue">李雷宝宝</text>
					<text>今天是李雷宝宝第一天上学，加油！</text>
				</view>
				
			</view>
			<view class="bottom">
				<image src="../../../../static/index_bottom1.jpg" mode="aspectFill"></image>
				<image src="../../../../static/index_bottom2.jpg" mode="aspectFill"></image>
				<image src="../../../../static/index_bottom1.jpg" mode="aspectFill"></image>
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
	.top_bg{
		width:100%;height:272upx;
		background:url('../../../../static/bg.jpg')no-repeat  center;
		background-size:contain;
	}
	.tab{
		width:100%;height:400upx;
		display: flex;
		justify-content:center;
		flex-direction: column;
		padding:40upx;
	}
	.tab .top{
		width:100%;height:160upx;
		display: flex;
		flex-direction: row;
	}
	.top .tx_image{
		width:80upx;height:80upx;
	}
	.tx_image image{
		width:100%;height:100%;
		border-radius:50%;
	}
	.top .name text{
		display:block;
		width:468upx;height:60upx;
		line-height: 80upx;
		padding-left:20upx;
	}
	.top .name .blue{
		color:#0A98D5;
		font-weight: 600;
	}
	.tab .bottom{
		width:600upx;height:120upx;
		display: flex;
		justify-content: center;
		flex-direction: row;
		flex-wrap: wrap;
		align-content: center;
		margin-left:60upx;
	}
	.bottom image{
		width:30%;height:100%;
		padding-right: 20upx;
	}
</style>
