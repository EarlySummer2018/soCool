<template>
	<view class="sc-search">
		<input class="sc-search_input" type="text" placeholder="请输入收缩关键字" :value="props.keywords"
			@input="changeKeywords($event)" />
	</view>
</template>

<script lang="ts" setup>
	import {
		ref
	} from 'vue'
	interface Props {
		keywords: string
		height ? : string | number
	}
	const props = withDefaults(defineProps < Props > (), {
		keywords: '123',
		height: '40px'
	})
	const emit = defineEmits(['update:keywords'])

	const timer: NodeJS.Timeout = ref(null)
	const changeKeywords = (ev) => {
		emit('update:keywords', ev.detail.value)
	}
</script>

<style lang="scss" scoped>
	.sc-search {
		width: 100%;
		height: v-bind('props.height');

		&_input {
			height: v-bind('props.height');
			font-size: 24rpx;
			background-color: pink;
		}
	}
</style>
