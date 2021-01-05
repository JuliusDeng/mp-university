<template>
	<view>
		<!-- 自定义导航 -->
		<view class="bg-blue" :style="{height:CustomBar + 'px'}">
			<view class="d-flex a-center" :style="style">
				<image src="../../static/index/cquni.jpg" :style="imgSize" class="ml-2 rounded-half"></image>
				<view class="text-white ml-2 font-33">重庆大学校园服务号</view>
			</view>
		</view>
		
		 
		
	</view>
</template>

<script>
	import uniNavBar from "@/components/uni-nav-bar/uni-nav-bar.vue"
	
	export default {
		components: {
			uniNavBar
		},
		data() {
			return {
				StatusBar: this.StatusBar,
				CustomBar: this.CustomBar,
				CustomBarUse: this.CustomBarUse
			}
		},
		onLoad() {

		},
		computed: {
			style() {
				const StatusBar = this.StatusBar
				const CustomBar = this.CustomBar
				console.log("StatusBar",StatusBar);
				console.log("CustomBar",CustomBar);
				const style = `height:${CustomBar}px;padding-top:${StatusBar}px;`
				console.log("style", style);
				return style
			},
			imgSize() {
				const StatusBar = this.StatusBar
				const _size = this.CustomBarUse
				const imgSize = `height:${_size}px; width:${_size}px;`
				return imgSize
			}
		},
		methods: {

		}
	}
</script>

<style>
	 .status_bar {
	      height: var(--status-bar-height);
	      width: 100%;
	  }
	
	
	
</style>
