<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	@import './common/uni.css';
	/*每个页面公共css */
	*{
		padding:0;
		margin:0;
		font-family: "SimHei YouYuan";
		box-sizing: border-box;
	}
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
</style>
