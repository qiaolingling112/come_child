<template>
	<view>
		<view class="cont">
			<text>补充资料1</text>
			<view><image src="../../../static/001.jpg" mode="aspectFill"></image></view>
			<text>补充资料2</text>
			<view><image src="../../../static/002.jpg" mode="aspectFill"></image></view>
			<text>补充资料3</text>
			<view><image src="../../../static/003.jpg" mode="aspectFill"></image></view>
			<text>补充资料4</text>
			<view><image src="../../../static/001.jpg" mode="aspectFill"></image></view>
		</view>
		<view class="btn">
			<button @tap="pass" class="ok">通过</button>
			<button @tap="nopass" class="no">拒绝</button>
		</view>
	</view>
</template>
<script>
	export default {
		data() {
			return {
				photoList:[]
			}
		},
		onLoad() {
			/*uni.request({
				url:"http://localhost/photoDetail",
				method:"GET",
				data:{stat:true},
				success:result=>{
					console.log(result.data.data)
					this.photoList.push(result.data.data);
					console.log(this.photoList)
				},
				fail:result=>{
					console.log(result)
				}
			})*/
		},
		methods: {
			scroll: function(e) {
				console.log(e)
				this.old.scrollTop = e.detail.scrollTop
			},
			pass(){
				uni.redirectTo({
					url:"../teacher-check/teacher-check"
				})
			},
			nopass(){
				uni.showModal({
					title:"确定要拒绝吗",
					icon:"none"
				})
			}
		}
	}
</script>

<style>
	.tit{
		width:100%;height:100upx;
		line-height:80upx;
		display: inline-block;
		background: #B2B2B2;
		color:#fff;
		text-align: center;
	}
	.cont{
		margin-top:40upx;
	}
	.cont text{
		margin-left:36upx;
	}
	.cont view{
		width:90%;
		height:300upx;
		line-height:300upx;
		border:2upx solid #8F8F94;
		border-radius: 16upx;
		text-align: center;
		margin:10upx auto;
	}
	image{
		width:100%;height:300upx;
	}
	.btn{
		width:100%;
	}
	button{
		background:#F0AD4E;
		color:#fff;
		margin-top:20upx;
	}
	.btn .ok{
		width:80%;
		float:left;
	}
	.btn .no{
		width:20%;
		float:left;
		background:#DD524D;
	}
</style>
