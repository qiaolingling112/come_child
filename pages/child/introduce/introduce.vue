<template>
	<view class="content">
		<!-- <text class="tit">欢迎报名我校！！！</text> -->
		<image src="../../../static/title.png" mode="aspectFill" class="tit"></image>
		<!--广告图片-->
		<view class="photo-sl">
			<view @tap="gotoDetail">
				<image src="../../../static/index_1.jpg" mode="aspectFill"></image>
				<text>拥有童心便拥有甜美幸福，拥有童心便拥有新奇幻想...</text>
			</view>
			<view @tap="gotoDetail">
				<image src="../../../static/index_2.jpg" mode="aspectFill"></image>
				<text>我园娱乐设施齐全，让孩子拥有一个多彩童年，开心快乐中成长</text>
			</view>
			<view @tap="gotoDetail">
				<image src="../../../static/index_1.jpg" mode="aspectFill"></image>
				<text>拥有童心便拥有甜美幸福，拥有童心便拥有新奇幻想...</text>
			</view>
			<view @tap="gotoDetail">
				<image src="../../../static/index_2.jpg" mode="aspectFill"></image>
				<text>我园娱乐设施齐全，让孩子拥有一个多彩童年，开心快乐中成长</text>
			</view>
		</view>
		<!--校园简介-->
		<view class="mes">
			<h3>园所简介</h3>
			<text>艾华集团幼儿园（儿童中心）创办于2016年4月，是湖南艾华集团股份有限公司旗下的一所经赫山区教育局批准创办的幼儿园，经过2年多的历练，从无到有，现已发展为现代化、高起点的幼儿园，现有园舍占地面积800余平方米，户外活动场地约300余平方米，现有大、中、小班级，幼儿60余名，园长1名，教师5名，保育员1名，均含有教师资格证，证书达标率100%。</text></view> 
		<!--轮播图-->
		<view class="uni-margin-wrap">
			<swiper class="swiper" :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
				<swiper-item>
					<view class="swiper-item">
						<image src="../../../static/index_bottom1.jpg" mode="aspectFill"></image>
						<text>孩子上课不专心怎么办？</text>
					</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item">
						<image src="../../../static/index_bottom2.jpg" mode="aspectFill"></image>
						<text>遇到校园欺凌怎么教孩子处理？</text>
					</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item">
						<image src="../../../static/index_bottom3.jpg" mode="aspectFill"></image>
						<text>学习总是跟不上怎么办？</text>
					</view>
				</swiper-item>
			</swiper>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				indicatorDots: true,
				autoplay: true,
				interval: 2000,
				duration: 500,
				indexList:[]
			}
		},
		onLoad() {
		/*	uni.request({
				url:"",
				method:"GET",
				data:{stat:true},
				success:e=>{
					//console.log(e.data.data)
					this.indexList.push(e.data.data);
					console.log(this.indexList)
					},
				fail:e=>{console.log(e)}
			*/
		},
		methods: {
			gotoDetail:function(){
				uni.navigateTo({
					url:'introduce_detail/introduce_detail'
				})
			}
		}
	}
</script>

<style>
	.content .tit{
		display: inline-block;
		width:100%;height:150upx;
		font-size:36upx;
		color:#fff;
		text-align: center;
	}
	.content .mes{
		width:80%;height:440upx;
		line-height: 40upx;
		padding:20upx;
		border:2upx solid #E5E5E5;
		border-radius:15upx;
		text-align: center;
	}
	.content h3{
		color:#0A98D5;
	}
	.uni-margin-wrap {
		width:95%;height:300upx;
		margin-top:60upx;
		border:2upx solid #000;
		border-radius: 16upx;
	}
	.uni-margin-wrap image{
		width:100%;height:100%;
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
	.uni-margin-wrap text{
		font-size:24upx;
		color:#000;
		background:#fff;
	}
	.content .photo-sl{
		width:100%;
		height:1200upx;
		text-align: center;
		display: flex;
		justify-content: space-between;
		flex-wrap: wrap;
		align-items: center;
		flex-direction: row;
	}
	.content .photo-sl view{
		width:80%;height:240upx;
		border:2upx solid #000;
		margin:20upx 60upx;
		border-radius: 16upx;
		display: flex;
		justify-content: space-between;
		align-items: stretch;
		padding:20upx;
		flex-direction: row;
	}
	.photo-sl image{
		width:60%;height: 200upx;
		border:2upx solid #000;
		border-radius: 16upx;
	}
	.photo-sl text{
		display: inline-block;
		width:30%;height:200upx;
		overflow:hidden;
		font-size: 24upx;
		line-height: 50upx;
	}
</style>
