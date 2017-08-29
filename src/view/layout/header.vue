<template>
	<div class="headSearch">
		<div class="locate">
			<span>广州</span>
			<i class="fa fa-angle-down" aria-hidden="true"></i>
		</div>
		<mt-search :value.sync="value" cancel-text="取消" placeholder="疾病/医院/科室/医生等">
		</mt-search>
	</div>
</template>

<script>
	export default {
		data(){
			return {
				name:"index"
			}
		}
	}

</script>

<style>
/*头部*/
.headSearch{
	position: relative;
    width: 100%;
    height: 50px;
    margin-bottom: 10px;
    display: inline-block;
    z-index: 1;
}
.locate{
	position: absolute;
	display: inline-block;
	top: 50%;
    left: 3%;
    font-size: 0.8rem;
}
.mint-searchbar-cancel{
	font-size: 0.8rem;
}
.mint-search{
	height: 100%;
	margin: 10px 0px 10px 50px;
}
.mint-searchbar{
    border-radius: 30px;
    background-color: #E0E0E0;
    margin-left: 20px;
}
.mint-searchbar-inner{
    border-radius: 20px;
}
.mint-searchbar-inner input{
    margin-left: 5px;	
}	

</style>