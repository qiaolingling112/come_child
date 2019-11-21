<template>
	<view class="content">
		<h2>欢迎报名小精灵幼儿园，请您仔细填写以下资料！</h2>
		<view class="main">
			<text>step1 填写基本资料</text>
			<form action="post" @submit="formSubmit">
				<table class="cl-info">
					<tr>
						<td>姓名 </td>
						<td><input type="text" name="uname" v-model="nameTest"></td>
					</tr>
					<tr>
						<td>性别</td>
						<td>
							<radio-group class="form-radio-gap uni-flex" name="gender" style="transform:scale(1)">
								<label>
									<radio value="男" id="boy" />男
								</label>
								<label>
									<radio value="女" id="girl" />女
								</label>
							</radio-group>
						</td>
					</tr>
					<tr>
						<td>年龄</td>
						<td>
							<input type="text" v-model="age">
						</td>
					</tr>
					<tr>
						<td>身高(cm)</td>
						<td><input type="text" v-model="heit" /></td>
					</tr>
					<tr>
						<td>体重(kg)</td>
						<td><input type="text" v-model="heavy"></td>
					</tr>
				</table>
				<text>step2 监护人基本资料</text>
				<table class="cl-info">
					<tr>
						<td>姓名</td>
						<td><input type="text" v-model="nameTest2"></td>
					</tr>
					<tr>
						<td>与申请人关系</td>
						<td>
							<input type="text" v-model="parent">
						</td>
					</tr>
					<tr>
						<td>监护人手机号</td>
						<td><input type="text" v-model="phoneno"></td>
					</tr>
				</table>
				<button type="default" size="default" class="btn-submit" formType="submit" @tap="jump">报名</button>
			</form>
		</view>
		
	</view>
</template>

<script>
	var graceChecker = require('@/common/graceChecker.js');
	var data;
	var _self;
	export default {
		data() {
			return {
				index: 0,
				nameTest: '',
				age:'',
				heit:'',
				heavy:'',
				parent:'',
				phoneno:'',
				nameTest2:''
			}
		},
		onload() {
			_self = this
		},
		methods: {
			jump(){
				uni.redirectTo({
					url:"child-check/child-check"
				})
			},
			formSubmit: function(e) {
				/*姓名验证
				if (this.nameTest == "") {
					uni.showToast({
						title: '姓名不能为空',
						icon: 'none'
					})
				return
				} else if (this.nameTest.length < 2 || this.nameTest.length>4) {

					uni.showToast({
						title: '请输入正确的姓名',
						icon: 'none'
				})
					return
 				}*/
				var rule = [
				/*	{
						name:'gender',
						checkType:'in',
						checkRule:'男,女',
						errorMsg: '请选择性别'
					},
					{
						name:'yeno',
						checkType:'in',
						checkRule:'是,否',
						errorMsg: '请选择是否有接种证明'
					},*/
				];
				/*判断年龄
				if(this.age==""){
					uni.showToast({
						title:'请输入年龄',
						icon:'none'
					})
				return
				}else if(this.age<3 || this.age>6){
					uni.showToast({
						title:'请输入正确的年龄',
						icon:'none'
					})
				return
				}*/
				/*验证身高
				if(this.heit==""){
					uni.showToast({
						title:'请输入身高',
						icon:'none'
					})
				return
				}else if(this.heit<85 || this.heit>120){
					uni.showToast({
						title:'请输入正确的身高',
						icon:'none'
					})
				return
				}*/
				/*体重验证
				if(this.heavy==""){
					uni.showToast({
						title:'请输入体重',
						icon:'none'
					})
				return
				}else if(this.heavy<25 || this.heavy>56){
					uni.showToast({
						title:'请输入正确的体重',
						icon:'none'
					})
				return
				}*/
				/*验证监护人姓名
				if(this.nameTest2==""){
					uni.showToast({
						title:'请输入监护人姓名',
						icon:'none'
					})
				return
				}else if(this.nameTest2.length<2 || this.nameTest2.length>4){
					uni.showToast({
						title:'请输入正确的监护人姓名',
						icon:'none'
					})
				return
				}*/
				/*验证关系
				if(this.parent==""){
					uni.showToast({
						title:'请输入关系',
						icon:'none'
					})
				return
				}else if(this.parent.length>=3){
					uni.showToast({
						title:'请输入正确的关系',
						icon:'none'
					})
				return
				}*/
				/*验证手机号
				var regP=/^1(3|4|5|6|7|8|9)\d{9}$/;
				if(this.phoneno==""){
					uni.showToast({
						title:'请输入手机号',
						icon:'none'
					})
				return
				}else if(!regP.test(this.phoneno)){
					uni.showToast({
						title:'请输入正确的手机号',
						icon:'none'
					})
				return
				}*/
					/*if (checkRes) {
						uni.showToast({
							title:'验证通过',
							icon: 'none'
						});
						console.log(formData);
						this.$router.push('/pages/child-check/child-check')
					} else {
						uni.showToast({
							title: graceChecker.error,
							icon: 'none'
						});
					}
				}
			},*/
			/*bindPickerChange: function(e) {
				data = e.target.value;
				this.index = e.target.value
			}*/
		},
	},
}
</script>

<style>
	.content h2{
		width:100%;height:60upx;
		line-height:60upx;
		font-weight: normal;
		font-size: 30upx;
	}
	.content text {
		display: inline-block;
		width: 100%;
		height: 100upx;
		line-height: 100upx;
		text-align: center;
		font-weight: bold;
		background:#DD524D;
		color: #fff;
		margin: 0;
		padding: 0;
	}
	/* .content .main{
		width:100%;height:1200upx;
		padding-top:40upx;
	} */
	.content .cl-info {
		height: 520upx;
	}
	
	.content form table {
		margin-left:40upx;
		
	}
	.content form .cl-info:first-child tr td{
		padding-right: 125upx;
	}
	.content form .cl-info:first-child tr:nth-child(4) td{
		padding-right:70upx;
	}
	.content form .cl-info:first-child tr:last-child td{
		padding-right:80upx;
	}
	.content form .cl-info:nth-child(3) {
		height: 320upx;
	}
	.content form .cl-info:nth-child(3) tr:first-child td{
		padding-right:125upx;
	}
	.content .cl-info tr {
		margin-top: 30upx;
		width:100%;
		display: inline-flex;
	}
	.content .cl-info td {
		padding-right:20upx;
	}
	.content .cl-info input {
		border: 2upx solid #B2B2B2;
		border-radius: 20upx;
		text-indent: 12upx;
		font-size: 26upx;
	}

	.content .cl-info input,
	.content .cl-info select {
		width: 360upx;
		height: 60upx;
	}

	.content button {
		width: 100%;
		height:100upx;
		line-height:100upx;
		background: #DD524D;
		color: #fff;
		margin-top: 40upx;
		margin-bottom:0upx;
		font-weight: bold;
		font-size:28upx;
	}
</style>
