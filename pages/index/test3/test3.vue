<template>
	<view>
		<button @click="set" type="primary">setStorageSync</button>
		<button @click="get" type="primary">getStorage</button>
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
			},
			get()
			{
				uni.getStorage({
					key:'b',
					success: (data) => {
						console.log(data);
						uni.showToast({
							icon: 'success',
							title: "读取成功："+data.data,
						})
					},
					fail: (err) => {
						console.log(err);
						uni.showToast({
							icon: 'success',
							title: "读取失败"
						})
					}
				})
				console.log(2);
			}
		}
	}
</script>

<style>
button
{
	margin: 10px;
}
</style>