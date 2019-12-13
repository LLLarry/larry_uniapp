<template>
	<view class="index">

		<view class="card">
			<view class="top">
				<view class="userInfo">
					<image src="/static/demo/demo5.jpg" mode="widthFix"></image>
					<text>鲁大师</text>
				</view>
				<view class="add">
					<view class="icon iconfont">&#xe684;</view>
					<text>关注</text>
				</view>
			</view>
			<text class="title">
				走出去，才发现你跟别人差的不是一点半点
			</text>
			<view class="middle">
				<image src="../../static/demo/datapic/11.jpg" mode="widthFix"></image>
			</view>
			<view class="bottom">
				<view class="left">
					<view class="icon_item">
						<view class="icon_list icon iconfont">&#xe650;</view>
						<view class="icon_list">570</view>
					</view>
					<view class="icon_item">
						<view class="icon_list icon iconfont">&#xe600;</view>
						<view class="icon_list">853</view>
					</view>
				</view>
				<view class="right">
					<view class="icon_item">
						<view class="icon_list icon iconfont">&#xe60f;</view>
						<view class="icon_list">570</view>
					</view>
					<view class="icon_item">
						<view class="icon_list icon iconfont">&#xe627;</view>
						<view class="icon_list">853</view>
					</view>
				</view>
			</view>
		</view>
		
		<view class="card">
			<view class="top">
				<view class="userInfo">
					<image src="/static/demo/demo5.jpg" mode="widthFix"></image>
					<text>鲁大师</text>
				</view>
				<view class="add">
					<view class="icon iconfont">&#xe684;</view>
					<text>关注</text>
				</view>
			</view>
			<text class="title">
				走出去，才发现你跟别人差的不是一点半点
			</text>
			<view class="middle">
				<image src="../../static/demo/datapic/11.jpg" mode="widthFix"></image>
			</view>
			<view class="bottom">
				<view class="left">
					<view class="icon_item">
						<view class="icon_list icon iconfont">&#xe650;</view>
						<view class="icon_list">570</view>
					</view>
					<view class="icon_item">
						<view class="icon_list icon iconfont">&#xe600;</view>
						<view class="icon_list">853</view>
					</view>
				</view>
				<view class="right">
					<view class="icon_item">
						<view class="icon_list icon iconfont">&#xe60f;</view>
						<view class="icon_list">570</view>
					</view>
					<view class="icon_item">
						<view class="icon_list icon iconfont">&#xe627;</view>
						<view class="icon_list">853</view>
					</view>
				</view>
			</view>
		</view>
		
		<view class="card">
			<view class="top">
				<view class="userInfo">
					<image src="/static/demo/demo5.jpg" mode="widthFix"></image>
					<text>鲁大师</text>
				</view>
				<view class="add">
					<view class="icon iconfont">&#xe684;</view>
					<text>关注</text>
				</view>
			</view>
			<text class="title">
				走出去，才发现你跟别人差的不是一点半点
			</text>
			<view class="middle">
				<image src="../../static/demo/datapic/11.jpg" mode="widthFix"></image>
			</view>
			<view class="bottom">
				<view class="left">
					<view class="icon_item">
						<view class="icon_list icon iconfont">&#xe650;</view>
						<view class="icon_list">570</view>
					</view>
					<view class="icon_item">
						<view class="icon_list icon iconfont">&#xe600;</view>
						<view class="icon_list">853</view>
					</view>
				</view>
				<view class="right">
					<view class="icon_item">
						<view class="icon_list icon iconfont">&#xe60f;</view>
						<view class="icon_list">570</view>
					</view>
					<view class="icon_item">
						<view class="icon_list icon iconfont">&#xe627;</view>
						<view class="icon_list">853</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
.index {
	
}
.card {
	padding: 24upx;
	/* background-color: #f5f7fa; */
	border-bottom: 2upx solid #eee;
}
.card .top{
	display: flex;
	justify-content: space-between;
	align-items: center;
	margin-bottom: 27upx;
}
.card .top .userInfo {
	display: flex;
	justify-content: space-between;
	align-items: center;
}
.card .top .userInfo image {
	width: 90upx;
	height: 90upx;
	border-radius: 100%;
}
.card .top .userInfo text{
	color: #999999;
	margin-left: 10upx;
}
.card .top  .add {
	display: flex;
	justify-content: space-between;
	align-items: center;
	color: #000;
	background-color: #f4f4f4;
	padding: 5upx 15upx;
	border-radius: 4upx;
}
.card .title {
	font-size: 32upx;
	color: #000;
	/* margin: 27upx 0 48upx; */
}
.card .middle {
	margin-top: 48upx;
}
.card .middle image {
	width: 100%;
	height: 380upx;
	border-radius: 10upx;
}
.card .bottom{
	display: flex;
	justify-content: space-between;
	align-items: center;
	padding: 24upx 0;
}
.card .bottom>view {
	display: flex;
}
.card .bottom .icon_item{
	display: flex;
	justify-content: space-between;
	align-items: center;
	
}
.card .bottom .icon_item>view {
	color: #d5d5d5;
}
.card .bottom .icon_item>view:nth-child(1) {
	margin-right: 15upx;
}
.card .bottom .icon_item:nth-child(2){
	margin-left: 20upx;
}
</style>
