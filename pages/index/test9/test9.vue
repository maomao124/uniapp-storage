<template>
	<view>
		<button @click="set" type="primary">setStorageSync</button>
		<button @click="get" type="primary">getStorageSync</button>
		<button @click="clear" type="primary">clearStorage</button>
		<button @click="clearSync" type="primary">clearStorageSync</button>
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
				try {
					uni.setStorageSync('b', '222');
					console.log('1');
					uni.showToast({
						icon: 'success',
						title: "写入成功",
					})
				} catch (e) {
					console.log("写入错误");
				}
				console.log("2");
			},
			get() {
				try {
					const data = uni.getStorageSync("b");
					console.log(data);
					uni.showToast({
						icon: 'success',
						title: "读取成功：" + data,
					})
				} catch (e) {
					uni.showToast({
						icon: 'success',
						title: "读取失败"
					})
				}
				console.log(2);
			},
			clear()
			{
				console.log('执行clearStorage');
				uni.clearStorage();
			},
			clearSync()
			{
				console.log('执行clearStorageSync');
				uni.clearStorageSync();
			}
		}
	}
</script>

<style>
	button {
		margin: 10px;
	}
</style>