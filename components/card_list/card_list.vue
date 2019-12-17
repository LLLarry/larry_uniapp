<template>
	<view class="card_list animated fadeInLeft fast">
		<view class="card">
			<view class="top">
				<view class="userInfo">
					<image :src="list.userpic" mode="widthFix"></image>
					<text>{{list.username}}</text>
				</view>
				<view class="add" v-if="!list.isguanzhu" @click="handleIsSave(list)">
					<view class="icon iconfont">&#xe684;</view>
					<text>关注</text>
				</view>
			</view>
			<text class="title">
				{{list.title}}
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
				<image :src="list.titlepic" mode="widthFix"></image>
			</view>
			<view class="bottom">
				<view class="left">
					<view class="icon_item" :class="{active: list.infonum &&list.infonum.index == 1}" @tap="handleLeftIcon(list,1)">
						<view class="icon_list icon iconfont">&#xe650;</view>
						<view class="icon_list">{{list.infonum && list.infonum.dingnum}}</view>
					</view>
					<view class="icon_item" :class="{active: list.infonum && list.infonum.index == 2}" @tap="handleLeftIcon(list,2)">
						<view class="icon_list icon iconfont">&#xe600;</view>
						<view class="icon_list">{{list.infonum && list.infonum.cainum}}</view>
					</view>
				</view>
				<view class="right">
					<view class="icon_item">
						<view class="icon_list icon iconfont">&#xe60f;</view>
						<view class="icon_list">{{list.commentnum}}</view>
					</view>
					<view class="icon_item">
						<view class="icon_list icon iconfont">&#xe627;</view>
						<view class="icon_list">{{list.sharenum}}</view>
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
				list: {}
				/* list:
					{
						userpic:"../../static/demo/userpic/12.jpg",
						username:"昵称",
						isguanzhu:false,
						title:"走出去，才发现你跟别人差的不是一点半点",
						type:"img", // img:图文,video:视频
						titlepic:"../../static/demo/datapic/11.jpg",
						infonum:{
							index:0,//0:没有操作，1:顶,2:踩；
							dingnum:11,
							cainum:11,
						},
						commentnum:10,
						sharenum:10,
					}, */
				
			}
		},
		props: ['list1'],
		created(){
			this.list= this.list1 //拿变量将通过props传过来的数据接收一下，放在list里面，不然的话uniapp原生app不能改变里面数据
		},
		methods: {
			handleIsSave(list){ //点击是否收藏
				list.isguanzhu= true
				uni.showToast({
					title: '关注成功'
				});
			},
			handleLeftIcon(list,from){
				switch(from){
					case 1:
					/* 点的顶 */
					if(list.infonum.index == 1){
						list.infonum.index= 0
						list.infonum.dingnum= list.infonum.dingnum-1
					}else if(list.infonum.index == 2){
						list.infonum.index= 1
						list.infonum.cainum= list.infonum.cainum-1
						list.infonum.dingnum= list.infonum.dingnum+1
					}else{
						list.infonum.index= 1
						list.infonum.dingnum= list.infonum.dingnum+1
					}
					break;
					case 2:
					/* 点的踩*/
					if(list.infonum.index == 2){
						list.infonum.index= 0
						list.infonum.cainum= list.infonum.cainum-1
					}else if(list.infonum.index == 1){
						list.infonum.index= 2
						list.infonum.cainum= list.infonum.cainum+1
						list.infonum.dingnum= list.infonum.dingnum-1
					}else{
						list.infonum.index= 2
						list.infonum.cainum= list.infonum.cainum+1
					}
					break;
				}
		}
	},
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
.card_list .card .bottom .icon_item.active>view {
	color: #FEDE33;
}
.card_list .card .bottom .icon_item>view:nth-child(1) {
	margin-right: 15upx;
}
.card_list .card .bottom .icon_item:nth-child(2){
	margin-left: 20upx;
}
</style>
