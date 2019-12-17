<template>
	<view class="index">
		<TabBarSwiper @childToFather="childToFather" :aIndex="activeIndex"/>
		
		<swiper class="swiper"
		:current="activeIndex"
		@change="scrollContent"
		:style="{height: height+'px'}"
		>
			<swiper-item v-for="(item,i) in conentList" :key="i">
				<template v-if="item.list.length > 0">
					<scroll-view
					scroll-y
					:style="{height: height+'px'}"
					@scrolltolower="handlePull(item,i)"
					>	
						<block v-for="(jtem,j) in item.list" :key="j">
							<CardList :list1="jtem"/>
						</block>
						<!-- 上拉加载 -->
						<LoadingMore :pullText="item.pullText" />
					</scroll-view>
				</template>
				<template v-else>
					<Nothing />
				</template>
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
	import TabBarSwiper from '../../components/tabBar_swiper/tabBar_swiper'
	import CardList from '../../components/card_list/card_list'
	import LoadingMore from '../../components/loading_more/loading_more'
	import Nothing from '../../components/nothing/nothing'
	export default {
		data() {
			return {
				title: 'Hello',
				activeIndex: 1,
				conentList: [
					{	
						pullText: '正在加载数据',
						list: [
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
							},
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
							},
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
							},
							]
					},
					{
						pullText: '正在加载数据',
						list: [{
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
							},]
					},
					{
						pullText: '正在加载数据',
						list: [{
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
							},]
					},
					{
						pullText: '正在加载数据',
						list: []
					},
					{
						pullText: '正在加载数据',
						list: [{
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
							},]
					},
					{
						pullText: '正在加载数据',
						list: [
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
							},
						]
					},
				],
				height: 400,
			}
		},
		components: {
			TabBarSwiper,
			CardList,
			LoadingMore,
			Nothing
		},
		onNavigationBarSearchInputClicked(){ //监听顶部原生输入框的点击事件
			/* 点击原生输入框，跳转到search页面 */
			uni.navigateTo({
				url: "/pages/search/search"
			})
		},
		onLoad() {
			
			uni.getSystemInfo({
			    success: (res)=>{
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
				if(item.pullText === '正在加载数据'){
					item.pullText= '加载中...'
					setTimeout(()=>{
						// 判断有没有数据，有数据则改成'正在加载数据'，没数据改为正在加载数据
						item.list.push({
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
							},)
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

</style>
