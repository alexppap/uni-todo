<script setup>
	import { onLaunch, onShow, onHide } from '@dcloudio/uni-app'

	onLaunch(() => {
		console.log('App Launch')
	})

	onShow(() => {
		console.log('App Show')
	})

	onHide(() => {
		console.log('App Hide')
	})
</script>

<style>
	/* 全局样式 */
	page {
		background-color: #F5F6FA;
		height: 100%;
		font-size: 28rpx;
		font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
	}

	/* 清除默认边距 */
	view, text {
		box-sizing: border-box;
	}

	/* 响应式容器 */
	.container {
		padding: 24rpx;
	}

	@media screen and (min-width: 768px) {
		.container {
			padding: 32rpx 48rpx;
			max-width: 1024px;
			margin: 0 auto;
		}
	}

	@media screen and (min-width: 1200px) {
		.container {
			padding: 40rpx 60rpx;
			max-width: 1440px;
			margin: 0 auto;
		}
	}

	/* 响应式显示/隐藏 */
	@media screen and (max-width: 767px) {
		.hidden-sm { display: none !important; }
		.visible-sm { display: block !important; }
	}

	@media screen and (min-width: 768px) and (max-width: 1199px) {
		.hidden-md { display: none !important; }
		.visible-md { display: block !important; }
	}

	@media screen and (min-width: 1200px) {
		.hidden-lg { display: none !important; }
		.visible-lg { display: block !important; }
	}
</style>
