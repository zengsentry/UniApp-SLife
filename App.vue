<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
			//读取本地缓存的设备信息
			uni.getStorage({
				key: 'SystemInfo',
				success(res) {
					if (res.data == null || res.data == undefined || res.data == '') {
						//this.getSystemInfo()
						//获取设备的信息
						uni.getSystemInfo({
							success(res) {
								console.log(res)
								//保存设备信息
								uni.setStorage({
									key: 'SystemInfo',
									data: res,
									success: function() {
										console.log('保存设备信息成功');
									}
								})
							}
						})
					}
				},
				fail() {
					//this.getSystemInfo()
					//获取设备的信息
					uni.getSystemInfo({
						success(res) {
							console.log(res)
							//保存设备信息
							uni.setStorage({
								key: 'SystemInfo',
								data: res,
								success: function() {
									console.log('保存设备信息成功');
								}
							})
						}
					})
				}
			})
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		},
	}
</script>

<style>
	/*每个页面公共css */
</style>
