<template>
	<view>
		<button @click="set" type="primary">setStorage</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {
			set() {
				uni.setStorage({
					key: 'a',
					data: 'abc',
					success() {
						console.log("1");
						uni.showToast({
							icon: 'success',
							title: "写入成功",
						})
					}
				})
				console.log("2");
			}
		}
	}
</script>

<style>

</style>