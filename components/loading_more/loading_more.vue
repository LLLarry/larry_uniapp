<template>
	<view>
		<view class="pullText">{{pullText}}</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		props: ['pullText']
	}
</script>

<style scope>
.pullText {
	text-align: center;
	padding: 15upx 0;
	color: #AAAAAA;
}
</style>
