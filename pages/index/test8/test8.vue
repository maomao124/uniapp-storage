<template>
	<view>
		<button @click="set" type="primary">setStorageSync</button>
		<button @click="get" type="primary">getStorageSync</button>
		<button @click="remove" type="primary">removeStorage</button>
		<button @click="removeSync" type="primary">removeStorageSync</button>
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
			remove() {
				uni.removeStorage({
					key: 'b',
					success: (res) => {
						console.log(res);
						uni.showToast({
							icon: 'success',
							title: "删除成功"
						})
					},
					fail: (err) => {
						console.log(err);
						uni.showToast({
							icon: 'fail',
							title: "删除失败"
						})
					}
				})
			},
			removeSync() {
				try {
					uni.removeStorageSync("b");
					uni.showToast({
						icon: 'success',
						title: "删除成功"
					})
				} catch (e) {
					console.log(err);
					uni.showToast({
						icon: 'fail',
						title: "删除失败"
					})
				}
			}
		}
	}
</script>

<style>
	button {
		margin: 10px;
	}
</style>