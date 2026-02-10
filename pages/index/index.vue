<template>
	<view class="page">
		<!-- 自定义导航栏 -->
		<view class="nav-bar" :style="{ paddingTop: statusBarHeight + 'px' }">
			<view class="nav-bar-inner">
				<view class="nav-btn" @click="goBack">
					<text class="nav-icon">&lt;</text>
				</view>
				<text class="nav-title">一船一成本</text>
				<view class="nav-btn" @click="closePage">
					<text class="nav-icon close-icon">×</text>
				</view>
			</view>
		</view>

		<!-- 占位，避免内容被导航栏遮挡 -->
		<view :style="{ height: (statusBarHeight + 44) + 'px' }"></view>

		<!-- 顶部 Banner -->
		<view class="banner">
			<view class="banner-content">
				<text class="banner-title">工业智脑</text>
				<!-- 船舶装饰图（使用 CSS 绘制简化版） -->
				<view class="banner-decoration">
					<view class="deco-line deco-line-1"></view>
					<view class="deco-line deco-line-2"></view>
					<view class="deco-line deco-line-3"></view>
				</view>
			</view>
		</view>

		<!-- 功能入口卡片 -->
		<view class="card-wrapper">
			<view class="entry-card" @click="goToOverview">
				<view class="card-bg-fallback"></view>
				<image class="card-bg" src="/static/ship-entry.png" mode="aspectFill" @error="imgError = true"></image>
				<view class="card-overlay"></view>
				<view class="card-content">
					<text class="card-title">一船一成本</text>
					<view class="card-arrow">
						<text class="arrow-text">→</text>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script setup>
	import { ref } from 'vue'
	import { onLoad } from '@dcloudio/uni-app'

	const statusBarHeight = ref(0)
	const imgError = ref(false)

	onLoad(() => {
		const sysInfo = uni.getSystemInfoSync()
		statusBarHeight.value = sysInfo.statusBarHeight || 0
	})

	const goBack = () => {
		uni.navigateBack({
			fail: () => {}
		})
	}

	const closePage = () => {
		uni.navigateBack({
			delta: 99,
			fail: () => {}
		})
	}

	const goToOverview = () => {
		uni.switchTab({
			url: '/pages/overview/index'
		})
	}
</script>

<style scoped>
	.page {
		min-height: 100vh;
		background-color: #F5F6FA;
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

	.close-icon {
		font-size: 44rpx;
	}

	.nav-title {
		font-size: 34rpx;
		font-weight: 600;
		color: #333333;
	}

	/* Banner */
	.banner {
		background: linear-gradient(135deg, #2979FF, #4B9AFF);
		padding: 40rpx 32rpx 80rpx;
		position: relative;
		overflow: hidden;
	}

	.banner-content {
		position: relative;
		z-index: 2;
	}

	.banner-title {
		font-size: 48rpx;
		font-weight: bold;
		color: #FFFFFF;
	}

	/* 装饰线条（模拟船舶线条） */
	.banner-decoration {
		position: absolute;
		right: -20rpx;
		top: -20rpx;
		width: 300rpx;
		height: 200rpx;
	}

	.deco-line {
		position: absolute;
		background-color: rgba(255, 255, 255, 0.15);
		border-radius: 100rpx;
		transform: rotate(-15deg);
	}

	.deco-line-1 {
		width: 280rpx;
		height: 8rpx;
		top: 40rpx;
		right: 0;
	}

	.deco-line-2 {
		width: 220rpx;
		height: 8rpx;
		top: 80rpx;
		right: 20rpx;
	}

	.deco-line-3 {
		width: 160rpx;
		height: 8rpx;
		top: 120rpx;
		right: 40rpx;
	}

	/* 功能入口卡片 */
	.card-wrapper {
		padding: 0 32rpx;
		margin-top: -40rpx;
		position: relative;
		z-index: 3;
	}

	.entry-card {
		position: relative;
		border-radius: 24rpx;
		overflow: hidden;
		height: 380rpx;
		box-shadow: 0 8rpx 32rpx rgba(0, 0, 0, 0.1);
	}

	.card-bg-fallback {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background: linear-gradient(135deg, #1a3a5c, #2a6496, #1e7a8a);
	}

	.card-bg {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
	}

	.card-overlay {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background: linear-gradient(180deg, rgba(0, 0, 0, 0) 40%, rgba(0, 0, 0, 0.5) 100%);
	}

	.card-content {
		position: absolute;
		bottom: 0;
		left: 0;
		right: 0;
		padding: 32rpx;
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: space-between;
	}

	.card-title {
		font-size: 32rpx;
		font-weight: 600;
		color: #FFFFFF;
	}

	.card-arrow {
		width: 64rpx;
		height: 64rpx;
		background-color: rgba(255, 255, 255, 0.2);
		border-radius: 50%;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.arrow-text {
		font-size: 36rpx;
		color: #FFFFFF;
	}
</style>
