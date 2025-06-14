<script>
	export default {
		onLaunch: function() {
			console.log('智能停车宝启动')
			// 初始化用户位置信息
			this.initLocation()
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		},
		methods: {
			initLocation() {
				// 获取用户位置权限
				uni.getLocation({
					type: 'gcj02',
					success: (res) => {
						console.log('位置获取成功:', res)
						// 存储位置信息到全局
						uni.setStorageSync('userLocation', {
							latitude: res.latitude,
							longitude: res.longitude
						})
					},
					fail: (err) => {
						console.log('位置获取失败:', err)
					}
				})
			}
		}
	}
</script>

<style>
	/* 智能停车宝 - 科技蓝主题全局样式 */
	
	/* 全局变量定义 */
	:root {
		--primary-color: #1890FF;
		--primary-dark: #0050B3;
		--primary-light: #E6F7FF;
		--success-color: #52C41A;
		--warning-color: #FAAD14;
		--error-color: #FF4D4F;
		--text-primary: #262626;
		--text-secondary: #8C8C8C;
		--text-light: #BFBFBF;
		--bg-primary: #FFFFFF;
		--bg-secondary: #F0F8FF;
		--border-color: #E8E8E8;
		--shadow-light: 0 2px 8px rgba(24, 144, 255, 0.1);
		--shadow-medium: 0 4px 16px rgba(24, 144, 255, 0.15);
		--border-radius: 12rpx;
		--border-radius-large: 16rpx;
	}
	
	/* 全局重置样式 */
	view, text, button, input, textarea, picker, scroll-view, swiper, image {
		box-sizing: border-box;
	}
	
	page {
		background-color: var(--bg-secondary);
		font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'PingFang SC', 'Hiragino Sans GB', 'Microsoft YaHei', sans-serif;
		color: var(--text-primary);
		line-height: 1.5;
	}
	
	/* 通用容器样式 */
	.container {
		padding: 32rpx;
	}
	
	.card {
		background: var(--bg-primary);
		border-radius: var(--border-radius-large);
		box-shadow: var(--shadow-light);
		padding: 32rpx;
		margin-bottom: 24rpx;
	}
	
	/* 按钮样式 */
	.btn {
		border-radius: var(--border-radius);
		padding: 24rpx 48rpx;
		font-size: 28rpx;
		font-weight: 500;
		border: none;
		cursor: pointer;
		transition: all 0.3s ease;
		display: inline-flex;
		align-items: center;
		justify-content: center;
		gap: 16rpx;
	}
	
	.btn-primary {
		background: linear-gradient(135deg, var(--primary-color) 0%, var(--primary-dark) 100%);
		color: white;
		box-shadow: var(--shadow-medium);
	}
	
	.btn-primary:active {
		transform: translateY(2rpx);
		box-shadow: var(--shadow-light);
	}
	
	.btn-secondary {
		background: var(--bg-primary);
		color: var(--primary-color);
		border: 2rpx solid var(--primary-color);
	}
	
	.btn-large {
		padding: 32rpx 64rpx;
		font-size: 32rpx;
		border-radius: var(--border-radius-large);
	}
	
	/* 文本样式 */
	.text-primary {
		color: var(--text-primary);
	}
	
	.text-secondary {
		color: var(--text-secondary);
	}
	
	.text-light {
		color: var(--text-light);
	}
	
	.text-brand {
		color: var(--primary-color);
	}
	
	.title-large {
		font-size: 48rpx;
		font-weight: 600;
		line-height: 1.2;
	}
	
	.title-medium {
		font-size: 36rpx;
		font-weight: 500;
		line-height: 1.3;
	}
	
	.title-small {
		font-size: 28rpx;
		font-weight: 500;
		line-height: 1.4;
	}
	
	.body-text {
		font-size: 24rpx;
		line-height: 1.5;
	}
	
	.caption {
		font-size: 20rpx;
		line-height: 1.4;
		color: var(--text-secondary);
	}
	
	/* 布局工具类 */
	.flex {
		display: flex;
	}
	
	.flex-column {
		flex-direction: column;
	}
	
	.flex-center {
		align-items: center;
		justify-content: center;
	}
	
	.flex-between {
		justify-content: space-between;
		align-items: center;
	}
	
	.flex-around {
		justify-content: space-around;
		align-items: center;
	}
	
	.flex-1 {
		flex: 1;
	}
	
	/* 间距工具类 */
	.mt-8 { margin-top: 16rpx; }
	.mt-12 { margin-top: 24rpx; }
	.mt-16 { margin-top: 32rpx; }
	.mt-24 { margin-top: 48rpx; }
	
	.mb-8 { margin-bottom: 16rpx; }
	.mb-12 { margin-bottom: 24rpx; }
	.mb-16 { margin-bottom: 32rpx; }
	.mb-24 { margin-bottom: 48rpx; }
	
	.p-8 { padding: 16rpx; }
	.p-12 { padding: 24rpx; }
	.p-16 { padding: 32rpx; }
	.p-24 { padding: 48rpx; }
	
	/* 状态样式 */
	.status-success {
		color: var(--success-color);
	}
	
	.status-warning {
		color: var(--warning-color);
	}
	
	.status-error {
		color: var(--error-color);
	}
	
	/* 渐变背景 */
	.gradient-bg {
		background: linear-gradient(135deg, var(--primary-color) 0%, var(--primary-dark) 100%);
	}
	
	.gradient-light-bg {
		background: linear-gradient(135deg, var(--primary-light) 0%, #FFFFFF 100%);
	}
	
	/* 动画效果 */
	.fade-in {
		animation: fadeIn 0.3s ease-in;
	}
	
	@keyframes fadeIn {
		from {
			opacity: 0;
			transform: translateY(20rpx);
		}
		to {
			opacity: 1;
			transform: translateY(0);
		}
	}
	
	.scale-in {
		animation: scaleIn 0.2s ease-out;
	}
	
	@keyframes scaleIn {
		from {
			transform: scale(0.9);
			opacity: 0;
		}
		to {
			transform: scale(1);
			opacity: 1;
		}
	}
</style>
