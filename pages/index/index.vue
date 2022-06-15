<template>
	<view class="content">
		<sc-search v-model:keywords="keywords" height="40px"></sc-search>
	</view>
</template>

<script lang="ts" setup>
	import {
		ref,
		watch
	} from 'vue'
	const keywords: string = ref('')
	watch(
		() => keywords.value,
		(val) => {
			console.log('keywords', val);
		})
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
