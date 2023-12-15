<template>
	<view>
		<button @click="get" type="primary">getStorageInfo</button>
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
				uni.getStorageInfo({
					success: (data) => {
						console.log(data);
						uni.showToast({
							icon: 'success',
							title: "读取成功"
						})
					}
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