<template>
	<view class="tabBar_swiper" >
		<scroll-view 
			:scroll-x="true"
			class="scroll-view"
			>
				<view 
				v-for="(item,i) in tabBarList" 
				:key="item.id" 
				class="scroll-view-item"
				:class="{'active': i== activeIndex}"
				@tap="toggleItem(i)"
				>
					<view class="name">{{item.name}}</view>
				</view>
		</scroll-view>
		
<!-- 		<swiper class="swiper"
		:current="activeIndex"
		@change="scrollContent"
		>
			<block v-for="(item,i) in conentList" :key="i">
				<swiper-item>
					<view class="swiper-item">{{item.content}}</view>
				</swiper-item>
			</block>
		</swiper> -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				tabBarList: [
					{name: '关注',id: 1},
					{name: '推荐',id: 2},
					{name: '体育',id: 3},
					{name: '热点',id: 4},
					{name: '财经',id: 5},
					{name: '娱乐',id: 6}
				],
				
				activeIndex: 1 //默认选中索引
			};
		},
		props: ['aIndex'],
		methods: {
			toggleItem(index){
				this.activeIndex= index
				this.$emit('childToFather',index)
			},
			
		},
		watch: {
			aIndex(newVal,oldValue){
				console.log(newVal)
				this.activeIndex= newVal
			}
		}
	}
</script>

<style>
.tabBar_swiper .scroll-view{
	white-space: nowrap;
	width: 100%;;
	display: flex;
	overflow: auto;
}
.tabBar_swiper .scroll-view .scroll-view-item {
	display: inline-block;
	padding: 24upx 42upx;
	font-size: 28upx;
	font-weight: bold;
	color: #8e8e8e;
}
.tabBar_swiper .uni-scroll-view {
	overflow: scroll !important;
}
.tabBar_swiper .active .name{
	color: #000000;
	position:relative;
}
.tabBar_swiper .active .name:after {
	content: '';
	height: 8upx;
	background-color: #FEDE33;
	border-radius: 8upx;
	position:absolute;
	left: 0;
	right: 0;
	bottom: -2upx;
	z-index: 5;
}

/* ::-webkit-scrollbar {
  width: 0;
  height: 0;
  color: transparent; 
  
} */
</style>
