<template>
	<view class="card_list">
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
				<view class="play">
					<view class="iconfont icon-bofang"></view>
				</view>
				<view class="play_info">
					<view class="play_info_item">
						<text>20W次播放</text>
						<text>2:47</text>
					</view>
				</view>
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
				
			}
		},
		methods: {
			
		}
	}
</script>

<style>
.card_list .card {
	padding: 24upx;
	/* background-color: #f5f7fa; */
	border-bottom: 2upx solid #eee;
}
.card_list .card .top{
	display: flex;
	justify-content: space-between;
	align-items: center;
	margin-bottom: 27upx;
}
.card_list .card .top .userInfo {
	display: flex;
	justify-content: space-between;
	align-items: center;
}
.card_list .card .top .userInfo image {
	width: 90upx;
	height: 90upx;
	border-radius: 100%;
}
.card_list .card .top .userInfo text{
	color: #999999;
	margin-left: 10upx;
}
.card_list .card .top  .add {
	display: flex;
	justify-content: space-between;
	align-items: center;
	color: #000;
	background-color: #f4f4f4;
	padding: 5upx 15upx;
	border-radius: 4upx;
}
.card_list .card .title {
	font-size: 32upx;
	color: #000;
	/* margin: 27upx 0 48upx; */
}
.card_list .card .middle {
	height: 380upx;
	margin-top: 48upx;
	position: relative;
}
.card_list .card .middle .play {
	position: absolute;
	left: 50%;
	top: 50%;
	-webkit-transform: translate(-50%,-50%);
	-moz-transform:  translate(-50%,-50%);
	-ms-transform:  translate(-50%,-50%);
	-o-transform:  translate(-50%,-50%);
	transform:  translate(-50%,-50%);
	color: rgba(255,255,255,.85);
	z-index: 1;
}
.card_list .card .middle .play_info {
	position: absolute;
	right: 10upx;
	bottom: 10upx;
	z-index: 1;
	line-height: 50upx;
	background-color: rgba(0,0,0,.5);
	color: #fff;
	padding: 0 10upx;
	border-radius: 50upx;
	font-size: 22upx
}
.card_list .card .middle .play_info .play_info_item text:first-child {
	margin-right: 10upx;
}
.card_list .card .middle .play>view {
	font-size: 120upx;	
}
.card_list .card .middle image {
	width: 100%;
	height: 380upx;
	border-radius: 10upx;
}
.card_list .card .bottom{
	display: flex;
	justify-content: space-between;
	align-items: center;
	padding: 24upx 0;
}
.card_list .card .bottom>view {
	display: flex;
}
.card_list .card .bottom .icon_item{
	display: flex;
	justify-content: space-between;
	align-items: center;
	
}
.card_list .card .bottom .icon_item>view {
	color: #d5d5d5;
}
.card_list .card .bottom .icon_item>view:nth-child(1) {
	margin-right: 15upx;
}
.card_list .card .bottom .icon_item:nth-child(2){
	margin-left: 20upx;
}
</style>
