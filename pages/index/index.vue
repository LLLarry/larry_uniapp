<template>
	<view class="index">
		<TabBarSwiper @childToFather="childToFather" :aIndex="activeIndex"/>
		
		<swiper class="swiper"
		:current="activeIndex"
		@change="scrollContent"
		:style="{height: height+'px'}"
		>
			<swiper-item v-for="(item,i) in conentList" :key="i">
				<scroll-view
				scroll-y
				:style="{height: height+'px'}"
				@scrolltolower="handlePull(item,i)"
				>	
					<block v-for="(jtem,j) in item.list" :key="j">
						<CardList :list="jtem"/>
					</block>
					<!-- 上拉加载 -->
					<LoadingMore :pullText="item.pullText" />
				</scroll-view>
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
	import TabBarSwiper from '../../components/tabBar_swiper/tabBar_swiper'
	import CardList from '../../components/card_list/card_list'
	import LoadingMore from '../../components/loading_more/loading_more'
	export default {
		data() {
			return {
				title: 'Hello',
				activeIndex: 1,
				conentList: [
					{	
						pullText: '正在加载数据',
						list: [{},{},{},{}]
					},
					{
						pullText: '正在加载数据',
						list: [{},{},{},{}]
					},
					{
						pullText: '正在加载数据',
						list: [{},{},{},{}]
					},
					{
						pullText: '正在加载数据',
						list: [{},{},{},{}]
					},
					{
						pullText: '正在加载数据',
						list: [{},{},{},{}]
					},
					{
						pullText: '正在加载数据',
						list: [{},{},{},{}]
					},
				],
				height: 400,
			}
		},
		components: {
			TabBarSwiper,
			CardList,
			LoadingMore
		},
		onLoad() {
			
			uni.getSystemInfo({
			    success: (res)=>{
			        console.log(res.screenHeight);
			        console.log(res.windowHeight);
			        console.log(uni.upx2px(86)) //自动转化upx
					//#ifdef APP-PLUS
					let height= res.windowHeight- uni.upx2px(86)- uni.upx2px(94)
					// #endif
					//#ifndef APP-PLUS
					let height= res.windowHeight- uni.upx2px(86)
					// #endif
					this.height= height
			    }
			});
			
		},
		methods: {
			scrollContent(e){
				this.activeIndex= e.detail.current	
			},
			childToFather(activeIndex){
				this.activeIndex= activeIndex
			},
			handlePull(item,index){ //上拉加载更多
				console.log(1)
				if(item.pullText === '正在加载数据'){
					console.log(2)
					item.pullText= '加载中...'
					setTimeout(()=>{
						console.log(3)
						// 判断有没有数据，有数据则改成'正在加载数据'，没数据改为正在加载数据
						item.list.push({})
						if(item.list.length >=7){
							item.pullText= '没有更过数据了'
						}else{
							item.pullText= '正在加载数据'
						}
					},1000)
				}else{
					
				}
			}
		}
	}
</script>

<style>
.index {
	
}


</style>
