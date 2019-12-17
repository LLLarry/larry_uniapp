<template>
	<view class="nothing">
		<image src="../../static/common/nothing.png" mode="widthFix"></image>
	</view>
</template>

<script>
</script>

<style scoped> 
/* 加入scoped是为了避免其他样式对其污染 */
	.nothing {
		position: absolute;
		left: 0;
		right: 0;
		top: 0;
		bottom: 0;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.nothing image {
		width: 50%;
	}
</style>
