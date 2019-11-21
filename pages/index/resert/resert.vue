<template>
	<view class="content">
		<view class="touxiang">
			<image src="../../../static/gotoScrol.jpg" mode="aspectFill"></image>
		</view>
		<form action="post" class="in" @submit="formSubmit">
			<input type="text" placeholder="请输入手机号" name="phoneno"><br>
			<input type="text" placeholder="验证码" name="yzm" value="">
			<span @tap="send">获取验证码</span><br>
			<button type="default" size="default" class="btn-submit" formType="submit">登录</button>
		</form>
	</view>
</template>
<script>
	var graceChecker = require('../../../common/graceChecker.js');
	export default {
		data() {
			return {
				resertList:[]
			}
		},
		onLoad() {
			/* uni.request({
				url:"http://localhost/padResert",
				data:{stat:true},
				method:"GET",
				success:result=>{
					console.log(result)
					this.resertList.push(result.data.data[0])
					console.log(this.resertList)
				},
				fail:result=>{
					console.log(result)
				}
			}) */
		},
		methods: {
			formSubmit: function(e) {
					//将下列代码加入到对应的检查位置
					//定义表单规则
					var rule = [
						/*{ name: 'phoneno', checkType: 'int', checkRule: '11', errorMsg: '手机号应为11位数字' },
						{ name: 'newPsd', checkType: 'int', checkRule: '3,9', errorMsg: '密码应为3-9位数字字母组成' },
						{ name: 'yzm', checkType: 'string', checkRule: '4', errorMsg: '验证码有误' }*/
					];
					//进行表单检查
					var formData = e.detail.value;
					var checkRes = graceChecker.check(formData, rule);
					if (checkRes) {
						uni.showToast({ title: '验证通过!', icon: 'none' });
						console.log(formData);
						uni.redirectTo({
							url:"../index"
						})
					} else {
						uni.showToast({ title: graceChecker.error, icon: 'none' });
					}
				},
				send(){
					uni.showToast({
						title:"验证码已发送"
					})
				}
			}
		}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
	.content .touxiang{
		width:180upx;height:180upx;
		text-align: center;
		margin-top:120upx;
	}
	.touxiang image{
		width:100%;height:100%;
		border-radius: 50%;
	}
	text{
		font-size:30upx;
		margin:40upx auto;
		color:#8F8F94;
	}
	.in{
		width:600upx;
		height:165upx;
		margin-top:20upx;
	}
	.in input{
		width: 600upx;height: 100upx;
		background: #FFFFFF;
		box-shadow: 10upx 0upx 20upx #C0C0C0;
		border-radius: 64upx;
		margin-top: 40upx;
		font-size: 30upx;
		letter-spacing:2upx;
		text-indent:36upx;
	}
	.in span{
		font-size: 28upx;
		display: inline-block;
		color:#999999;
		position:relative;
		top:-78upx;left:430upx;
	}
	.in button{
		border-radius: 64upx;
		color:#fff;height:100upx;
		line-height:100upx;
		background:#DD524D;
		font-size: 30upx;
		letter-spacing: 12upx;
	}
	.content .in .eye{
		display: inline-block;
		font-size:30upx;
		position:relative;
		left:540upx;
	}
</style>
