<script>
	import Vue from 'vue'
	export default {
		onLaunch: function() {
			console.log("onLaunch");
			uni.getSystemInfo({
				success: function(e) {
					console.log("getSystemInfo:", e);
					// APP端
					// #ifndef MP
					Vue.prototype.StatusBar = e.statusBarHeight;
					if (e.platform == 'android') {
						Vue.prototype.CustomBar = e.statusBarHeight + 50;
					} else {
						Vue.prototype.CustomBar = e.statusBarHeight + 45;
					};
					// #endif
					
					// #ifdef MP-WEIXIN
					// 微信端 状态栏 高度设置
					Vue.prototype.StatusBar = e.statusBarHeight;
					
					// 获取菜单按钮（右上角胶囊按钮）的布局位置信息。坐标信息以屏幕左上角为原点。
					let custom = wx.getMenuButtonBoundingClientRect();
					console.log("custom:", custom);
					Vue.prototype.Custom = custom;
					
					// 微信端 导航栏 高度设置
					Vue.prototype.CustomBar = custom.bottom + (custom.top - e.statusBarHeight);
					Vue.prototype.CustomBarUse = custom.bottom + (custom.top - e.statusBarHeight * 2);
					// #endif	
						
					// #ifdef MP-ALIPAY
					Vue.prototype.StatusBar = e.statusBarHeight;
					Vue.prototype.CustomBar = e.statusBarHeight + e.titleBarHeight;
					// #endif
				}
			})
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style lang="scss">
	/*每个页面公共css */
	@import "uview-ui/index.scss";
	
	@import "/common/common.css";
	@import "/common/yuchen.css";
	
	
</style>
