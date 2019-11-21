<template>
	<view>
		<!-- <view class="uni-list">
			<view class="uni-list-cell" hover-class="uni-list-cell-hover">
				<view class="uni-media-list uni-pull-right">
					 <view class="uni-media-list-logo">
						<button size="mini" class="btn" @tap="jump1">详情</button>
					</view>
					<view class="uni-media-list-body">
						<view class="uni-media-list-text-top">李雷</view>
						<view class="uni-media-list-text-bottom uni-ellipsis" @click="jump1">性别:男,年龄:5,身高95,体重16kg,性别:男,年龄:5,身高95,体重16kg</view>
					</view>
				</view>
			</view>
		</view> -->
		<!-- #ifndef MP-BAIDU || MP-ALIPAY || MP-TOUTIAO -->
		<view class="uni-list">
			<checkbox-group >
				<label class="uni-list-cell uni-list-cell-pd" v-for="(item,index) in items" :key="item.index">
					<view>
						<checkbox :value="item.id"  :class="{checked: item.checked}"
								@tap="check('list', index)"/>
					</view>
					<uni-swipe-action :options="options1">
						<uni-list-item  :show-arrow="false" :title="item.title" />
					</uni-swipe-action>
				</label>
			</checkbox-group>
		</view>
		<!-- #endif -->
		<view class="bottom_bar">
			<view class="check">
				<checkbox />
				<view class="all" @tap="check('all')">全选</view>
			</view>
			<view class="btns">
				<button type="primary" size="mini" @tap="pass">通过</button>
				<button type="warn" size="mini" @tap="no">拒绝</button>
			</view>
		</view>
	</view>
</template>
<script>
	import uniSwipeAction from '@/components/uni-swipe-action/uni-swipe-action.vue'
	import uniList from '@/components/uni-list/uni-list.vue'
	import uniListItem from '@/components/uni-list-item/uni-list-item.vue'
	export default {
		components: {
				uniSwipeAction,
				uniList,
				uniListItem
			},
		data() {
			return {
				allChecked:false,
				/* title: 'media-list',
				showImg: false, */
				items: [
					{title:'李雷,身高:105,体重:16kg,性别:男,李雷,身高:105,体重:16kg,性别:男',value:'李雷'},
					{title:'李雷,身高:105,体重:16kg,性别:男,李雷,身高:105,体重:16kg,性别:男',value:'韩梅梅'},
					{title:'李雷,身高:105,体重:16kg,性别:男,李雷,身高:105,体重:16kg,性别:男',value:'玛丽'},
					{title:'李雷,身高:105,体重:16kg,性别:男,李雷,身高:105,体重:16kg,性别:男',value:'沈腾'},
					{title:'李雷,身高:105,体重:16kg,性别:男,李雷,身高:105,体重:16kg,性别:男',value:'贾玲'},
					{title:'李雷,身高:105,体重:16kg,性别:男,李雷,身高:105,体重:16kg,性别:男',value:'沈阳'},
					{title:'李雷,身高:105,体重:16kg,性别:男,李雷,身高:105,体重:16kg,性别:男',value:'小宝'},
					{title:'李雷,身高:105,体重:16kg,性别:男,李雷,身高:105,体重:16kg,性别:男',value:'宝儿'},
					{title:'李雷,身高:105,体重:16kg,性别:男,李雷,身高:105,体重:16kg,性别:男',value:'小红'},
					{title:'李雷,身高:105,体重:16kg,性别:男,李雷,身高:105,体重:16kg,性别:男',value:'小明'},
					{title:'李雷,身高:105,体重:16kg,性别:男,李雷,身高:105,体重:16kg,性别:男',value:'小丽'}
				],
				isOpened: false,
				options1: [{
					text: '删除',
					style: {
						backgroundColor: '#dd524d'
					}
				}, {
					text: '确认',
					style: {
						backgroundColor: '#007aff'
					}
				}],
				options2: [{
					text: '删除',
					style: {
						backgroundColor: '#dd524d'
					}
				}, {
					text: '确认',
					style: {
						backgroundColor: '#007aff'
					}
				}],
				options3: [{
					text: '删除',
					style: {
						backgroundColor: '#dd524d'
					}
				}, {
					text: '确认',
					style: {
						backgroundColor: '#007aff'
					}
				}]
			}
		},
		onLoad() {
			/*setTimeout(() => {
				this.showImg = true;
			}, 400)
			uni.request({
				url:"http://localhost/childContent",
				data:{stat:true},
				method:"POST",
				header:{
					'content-type':'application/x-www-form-urlencoded'
				},
				success:e=>{
					console.log(e.data)
					this.list.push(e.data.data[0]);
					console.log(this.list)
				},
				fail:e=>{
					console.log(e)
				}
			})*/
			
		},
		onReady() {
			this.$nextTick(() => {
				this.isOpened = true
			})
		},
		methods: {
			bindClick(e) {
				console.log(e)
				uni.showToast({
					title: `点击了${e.content.text}按钮`,
					icon: 'none'
				})
			},
			setOpened() {
				this.isOpened = !this.isOpened
			},
			change(e) {
				this.isOpened = e
			},
			pass:function(){
				uni.navigateTo({
					url:'mes-detail/mes-detail'
				})
			},
			no:function(){
				uni.showModal({
					title:'提示',
					content:'确定要拒绝吗？',
					confirmText:'忍痛拒绝',
					cancelText:'在考虑下'
				})
			},
			/* checkboxChange: function (e) {
				var items = this.items,
					values = e.detail.value;
				for (var i = 0, lenI = items.length; i < lenI; ++i) {
					const item = items[i]
					if(values.indexOf(item.value) >= 0){
						this.$set(item,'checked',true)
					}else{
						this.$set(item,'checked',false)
					}
				}
			}, */
			//选中状态处理/未处理完成
			check(type, index){
				if(type === 'list'){
					this.items[index].checked = !this.items[index].checked;
				}else{
					const checked = !this.allChecked
					const list = this.items;
					list.forEach(list=>{
						list.checked = checked;
					})
					this.allChecked = checked;
				}
			},
			
		}
	}
</script>

<style>
	.btn{
		font-size:20upx;
		background: #DD524D;
		color:#fff;
	}
	uni-view.uni-swiper__box{
		width:80%;
	}
	.uni-checkbox .uni-checkbox-input{
		position: absolute;
		top:20upx;left:10upx;
	}
	.bottom_bar{
		width:100%;height:100upx;
		z-index: 999;
		background: #F1F1F1;
		position: fixed;
		bottom:0;left:0;right:0;
		border-top:2upx solid #E5E5E5;
		display: flex;
		justify-content:space-between;
		flex-direction: row;
		align-items: center;
	}
	.bottom_bar .check{
		width:50%;height:160upx;
		display: flex;
		flex-direction: row;
		align-items: center;
		padding-left:20upx;
	}
	.check .all{
		padding-left:36upx;
	}
	.bottom_bar .btns{
		width:50%;height:160upx;
		display: flex;
		justify-content: space-around;
		flex-direction: row;
		align-items: center;
		padding-right:20upx;
	}
</style>