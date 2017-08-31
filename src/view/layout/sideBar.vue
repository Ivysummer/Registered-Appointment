<template>
	<div class="sideBar">
		<span><i class="fa fa-bars" aria-hidden="true"></i></span>
	</div>
</template>

<script>
	export default {
		data(){
			return {

			}
		}
	}
</script>

<style>
.sideBar{
    overflow: hidden;
    margin-bottom: .5rem;
    background-color: #fafafa;
    position: fixed;
    width: 100%;
    height: 2rem;
    top: 0;
    left: 8px;
    z-index: 100;
}
.sideBar span{
    font-size: 1.5rem;
    width: 1.8rem;
    height: 1.8rem;
}

</style>