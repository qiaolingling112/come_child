<template>
	<view class="content">
		<text class="title">亲爱的家长，恭喜您的资料通过初审，为了方便更进一步了解您的孩子的详细情况，请继续补充以下资料，谢谢合作！</text>
		<view class="fgx"></view>
		<view class="uni-padding-wrap uni-common-mt">
			<text>补充资料一</text>
			<view class="demo">
				<block v-if="imageSrc">
					<image :src="imageSrc" class="image" mode="widthFix"></image>
				</block>
				<block v-else>
					<view class="upload" @tap="chooseImage">+</view>
				</block>
			</view>
		</view>
		<view class="uni-padding-wrap uni-common-mt">
			<text>补充资料二</text>
			<view class="demo">
				<block v-if="imageSrc">
					<image :src="imageSrc" class="image" mode="widthFix"></image>
				</block>
				<block v-else>
					<view class="upload" @tap="chooseImage">+</view>
				</block>
			</view>
		</view>
		<view class="uni-padding-wrap uni-common-mt">
			<text>补充资料三</text>
			<view class="demo">
				<block v-if="imageSrc">
					<image :src="imageSrc" class="image" mode="widthFix"></image>
				</block>
				<block v-else>
					<view class="upload" @tap="chooseImage">+</view>
				</block>
			</view>
		</view>
		<view class="uni-padding-wrap uni-common-mt">
			<text>补充资料四</text>
			<view class="demo">
				<block v-if="imageSrc">
					<image :src="imageSrc" class="image" mode="widthFix"></image>
				</block>
				<block v-else>
					<view class="upload" @tap="chooseImage">+</view>
				</block>
			</view>
		</view>
		<view class="uni-btn-v uni-common-mt">
			<button class="btn-submit" formType="submit" type="primary" @tap="over()">提交</button>
			<button type="default" formType="reset" class="resert">重置</button>
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				imageSrc:''
			}
		},
		onUnload() {
			this.imageSrc = '';
		},
		methods: {
			chooseImage: function() {
				uni.chooseImage({
					count: 1,
					sizeType: ['compressed'],
					sourceType: ['album'],
					success: (res) => {
						console.log('chooseImage success, temp path is', res.tempFilePaths[0])
						var imageSrc = res.tempFilePaths[0]
						uni.uploadFile({
							url: 'https://unidemo.dcloud.net.cn/upload',
							filePath: imageSrc,
							fileType: 'image',
							name: 'data',
							success: (res) => {
								console.log('uploadImage success, res is:', res)
								uni.showToast({
									title: '上传成功',
									icon: 'success',
									duration: 1000
								})
								this.imageSrc = imageSrc
							},
							fail: (err) => {
								console.log('uploadImage fail', err);
								uni.showModal({
									content: err.errMsg,
									showCancel: false
								});
							}
						});
					},
					fail: (err) => {
						console.log('chooseImage fail', err)
					}
				})
			},
			over(){
				uni.switchTab({
					url:"../child-check/child-check"
				})
			}
		}
	}
</script>

<style>
	.content .title{
		padding-left:20upx;
		padding-right:20upx;
	}
	.content text{
		text-indent: 50upx;
		margin-top:20upx;
	}
	.content .resert{
		background:#DD524D;
		color:#FFFFFF;
	}
	.fgx{
		width:100%;
		border-bottom:2upx solid #DD524D;
		margin-top:15upx;
	}
	.image {
		width: 100%;
	}
	
	.demo {
		background: #FFF;
		padding: 50upx;
	}
	.uni-hello-addfile{
		color:#808080;
		width:80upx;height:80upx;
	}
	.upload{
		width:200upx;height:200upx;
		line-height: 200upx;
		border:1px solid #000;
		font-size:24upx;
		text-align: center;
	}
	.uni-btn-v{
		width:100%;height:110upx;
		display: flex;
		justify-content: center;
		flex-direction: row;
		align-items: center;
	}
	.uni-btn-v button{
		width:50%;height:100%;
	}
</style>
