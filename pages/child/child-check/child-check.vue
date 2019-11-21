<template>
	<view>
		<view class="neirong">
			<image src="../../../static/success.png" mode="aspectFill" alt="提示图标"></image>
			<text>恭喜您！提交成功 <text class="three"> 3秒后</text>跳回首页</text>
		</view>
		<button @tap="jump()" class="btn">休息一下~</button>
		<view class="uni-margin-wrap">
			<swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
				<swiper-item>
					<view class="swiper-item">
						<image src="../../../static/index_1.jpg" mode="aspectFill"></image>
					</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item">
						<image src="../../../static/index_2.jpg" mode="aspectFill"></image>
					</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item">
						<image src="../../../static/index_bottom1.jpg" mode="aspectFill"></image>
					</view>
				</swiper-item>
			</swiper>
		</view>
	</view>
	
</template>

<script>
	var _self;
	export default {
		data() {
			return {
				indicatorDots: true,
				autoplay: true,
				interval: 2000,
				duration: 500,
				childList:[]
			}
		},
		onLoad() {
			_self = this;
			setTimeout(function() {
				_self.jump();
			}, 3000);
			/* uni.request({
				url:"http://localhost/childCheck",
				method:"GET",
				data:{
					stat:true
				},
				success:e=>{
					console.log(e.data.data[0]);
					this.childList.push(e.data.data[0])
					console.log(this.childList[0].content);
				},
				fail:e=>{
					console.log(e);
				}
			}) */
		},
		methods: {
			jump(){
				uni.switchTab({
					url:"../introduce/introduce"
				})
			}
		}
	}
</script>

<style>
 .neirong{
	width:90%;height:260upx;
	margin:20upx auto;
	padding-top:40upx;
	text-align: center;
	display: flex;
	justify-content: center;
	align-items: center;
	flex-direction: column;
}
.neirong image{
	width:26%;height:220upx;
}
.neirong text{
	font-size: 28upx;
}
.neirong text .three{
	color:#DD524D;
}
 .btn{
	width:80%;height:100upx;
	line-height: 100upx;
	background:#DD524D;
	color:#fff;
	margin-top:40upx;
	font-size:28upx;
	letter-spacing: 3upx;

}
	.uni-margin-wrap {
		width:90%;
		margin:120upx 30upx;
		border:2upx solid #000;
	}
	.swiper {
		height: 300upx;
	}
	.swiper-item {
		display: block;
		height: 300upx;
		line-height: 300upx;
		text-align: center;
	}
	.swiper-item text{
		font-size:36upx;
	}
</style>
