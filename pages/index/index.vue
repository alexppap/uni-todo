<template>
	<view class="page">
		<!-- 顶部安全区占位 -->
		<view :style="{ height: statusBarHeight + 'px' }"></view>

		<!-- 顶部 Banner -->
		<view class="banner">
			<view class="banner-content">
				<text class="banner-title">工业智脑</text>
			</view>
			<!-- 装饰：流线型弧线 -->
			<view class="banner-deco">
				<view class="deco-arc deco-arc-1"></view>
				<view class="deco-arc deco-arc-2"></view>
				<view class="deco-arc deco-arc-3"></view>
				<view class="deco-arc deco-arc-4"></view>
				<view class="deco-arc deco-arc-5"></view>
			</view>
		</view>

		<!-- 功能入口卡片 -->
		<view class="card-wrapper">
			<view class="entry-card" @click="goToOverview">
				<image class="card-bg" src="/static/ship-entry.png" mode="aspectFill"></image>
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

	onLoad(() => {
		const sysInfo = uni.getSystemInfoSync()
		statusBarHeight.value = sysInfo.statusBarHeight || 0
	})

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

	/* Banner */
	.banner {
		background: linear-gradient(135deg, #2979FF, #4B9AFF);
		padding: 40rpx 32rpx 40rpx;
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
		height: 100rpx;
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
		margin-top: 20rpx;
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
