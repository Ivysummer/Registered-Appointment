<template>
	<div class="index">
		<headerTop></headerTop>
		<router-view></router-view><!-- index下的子组件在此渲染 -->
		<Bottom></Bottom>
	</div>
</template>

<script>

	import headerTop from '@/view/layout/header'
	import Bottom from '@/view/layout/footer'

	export default {
		components: {headerTop,Bottom},
		data(){
			return {
				
			}
		}
	}

</script>

<style>
	

</style>