<template>
	<view>
		<button @click="set" type="primary">setStorageSync</button>
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
				try{
					uni.setStorageSync('b','222');
					console.log('1');
					uni.showToast({
						icon: 'success',
						title: "写入成功",
					})
				}catch(e){
					console.log("写入错误");
				}
				console.log("2");
			}
		}
	}
</script>

<style>

</style>