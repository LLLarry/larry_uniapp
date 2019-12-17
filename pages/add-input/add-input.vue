<template>
	<view class="add_input">
		<uniNavBar  
				left-icon="back" 
				:fixed="true"
				:status-bar="true" 
				right-text="发布"  
				@clickLeft="handleLeft"
				@clickRight="handleRight"
		>
			 <view class="tab_title" @tap="handleMid">
				 <view>{{tittle}}</view>
				 <view class="iconfont icon-xialazhankai"></view>
			 </view>
		</uniNavBar >
	</view>
</template>

<script>
	import uniNavBar  from '../../components/uni-nav-bar/uni-nav-bar'
	export default {
		data() {
			return {
				tittle: '所有人可见',
				tittleList: ['所有人可见','仅自己可见', '仅好友可见']
			}
		},
		components:{
			uniNavBar
		},
		methods: {
			handleLeft(){ //点击自定义导航栏的返回按钮
				uni.navigateBack({
					delta: 1
				});
			},
			handleRight(){ //点击自定义导航栏的右边按钮
				console.log('right')
			},
			handleMid(){ //点击导航中间
				uni.showActionSheet({
				    itemList: this.tittleList,
				    success: (res)=>{
						this.tittle= this.tittleList[res.tapIndex]
				        console.log('选中了第' + (res.tapIndex + 1) + '个按钮');
				    },
				    fail: (res)=>{
				        console.log(res.errMsg);
				    }
				});
			}
		}
	}
</script>

<style>
.status_bar {
  height: var(--status-bar-height);
  width: 100%;
}
.tab_title {
	width: 100%;
	display: flex;
	justify-content: center;
	align-content: center;
}
</style>
