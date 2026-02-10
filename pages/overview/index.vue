<template>
	<view class="page">
		<!-- 自定义导航栏 -->
		<view class="nav-bar" :style="{ paddingTop: statusBarHeight + 'px' }">
			<view class="nav-bar-inner">
				<view class="nav-btn" @click="goBackToHome">
					<text class="nav-icon">‹</text>
				</view>
				<text class="nav-title">一船一成本</text>
				<view class="nav-btn"></view>
			</view>
		</view>

		<!-- 占位，避免内容被导航栏遮挡 -->
		<view :style="{ height: (statusBarHeight + 44) + 'px' }"></view>

		<text class="placeholder-text">总览页（待开发）</text>
	</view>
</template>

<script setup>
	import { ref } from 'vue'
	import { onLoad } from '@dcloudio/uni-app'

	const statusBarHeight = ref(0)

	onLoad(() => {
		const sysInfo = uni.getSystemInfoSync()
		statusBarHeight.value = sysInfo.statusBarHeight || 0
	})

	const goBackToHome = () => {
		uni.reLaunch({
			url: '/pages/index/index'
		})
	}
</script>

<style scoped>
	.page {
		min-height: 100vh;
		background-color: #F5F6FA;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	/* 自定义导航栏 */
	.nav-bar {
		position: fixed;
		top: 0;
		left: 0;
		right: 0;
		z-index: 100;
		background-color: #FFFFFF;
	}

	.nav-bar-inner {
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: space-between;
		height: 44px;
		padding: 0 16rpx;
	}

	.nav-btn {
		width: 80rpx;
		height: 44px;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.nav-icon {
		font-size: 40rpx;
		color: #333333;
		font-weight: 300;
	}

	.nav-title {
		font-size: 34rpx;
		font-weight: 600;
		color: #333333;
	}

	.placeholder-text {
		font-size: 32rpx;
		color: #999999;
	}
</style>
