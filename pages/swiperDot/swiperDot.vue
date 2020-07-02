<template>
	<view class="dot-main">
			<view :class="['dot-item',current==index?'active':'']" v-for="(item,index) in list" :key="index"></view>
		</view>
</template>

<script>
	
	export default {
		props: [ 'list','current'],
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style>
.dot-main {
		display: flex;
		justify-content: center;
		align-items: center;
	}
	.dot-item {
		height: 10.41rpx;
		border-radius: 33.33rpx;
		width: 25rpx;
		background-color: #e5e5e5;
		margin: 0 6upx;
		box-sizing: border-box;
		margin-top: 29rpx;
	}
	.active {
		border-radius: 33.33rpx;
		width: 25rpx;
		background-color: #fba42f;
	}
</style>
