<template>
	<view>
		<button @click="get" type="primary">getStorageInfoSync</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {
			get() {
				const data = uni.getStorageInfoSync()
				console.log(data);
				uni.showToast({
					icon: 'success',
					title: "读取成功"
				})
			}
		}
	}
</script>

<style>
	button {
		margin: 10px;
	}
</style>