<template>
	<view class="index">
		<TabBar_swiper @childToFather="childToFather" :aIndex="activeIndex"/>
		
		<swiper class="swiper"
		:current="activeIndex"
		@change="scrollContent"
		:style="{'height': height+'px'}"
		>
			<block v-for="(item,i) in conentList" :key="i">
				<swiper-item>
					<scroll-view
					:scroll-y="true"
					:style="{'height': height+'px'}"
					>
						<Card_list />
						<Card_list />
						<Card_list />
						<Card_list />
					</scroll-view>
				</swiper-item>
			</block>
		</swiper>
	</view>
</template>

<script>
	import TabBar_swiper from '../../components/tabBar_swiper/tabBar_swiper'
	import Card_list from '../../components/card_list/card_list'
	export default {
		data() {
			return {
				title: 'Hello',
				activeIndex: 1,
				conentList: [
					{content: 'A'},
					{content: 'B'},
					{content: 'C'},
					{content: 'D'},
					{content: 'E'},
					{content: 'F'},
				],
				height: 400
			}
		},
		components: {
			TabBar_swiper,
			Card_list
		},
		onLoad() {
			let _this= this
			uni.getSystemInfo({
			    success: function (res) {
			        console.log(res.screenHeight);
			        console.log(res.windowHeight);
			        console.log(uni.upx2px(80)) //自动转化upx
				  let height= res.windowHeight- uni.upx2px(86)
				  _this.height= height
			    }
			});
		},
		methods: {
			scrollContent(e){
				this.activeIndex= e.detail.current	
			},
			childToFather(activeIndex){
				this.activeIndex= activeIndex
			}
		}
	}
</script>

<style>
.index {
	
}


</style>
