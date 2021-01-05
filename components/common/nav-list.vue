<template>
	<view class="mx-3 d-flex j-sb a-center">
		<view class="font-32">
			<text :class="icontype"></text><slot></slot>
		</view>
		<view class="text-muted">
			{{arrcontent}}<u-icon name="arrow-right"></u-icon>
		</view>
	</view>
</template>

<script>
	export default {
		props: {
			icontype: String,
			arrcontent: String
		},
		mounted() {
			console.log("icontype");
			console.log(this.icontype);
		}
	}
</script>

<style>
</style>
