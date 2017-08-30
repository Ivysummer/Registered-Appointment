<template>
	<div class="headSearch">
		<div class="locate">
			<span>广州</span>
			<span class="locateIcon"><i class="fa fa-angle-down" aria-hidden="true"></i></span>
		</div>
		<div class="innerSearch">
			<mt-search :value.sync="value" cancel-text="取消" placeholder="疾病/医院/科室/医生等">
		    </mt-search>
		</div>
	</div>
</template>

<script>
	export default {
		data(){
			return {
				value:''
			}
		}
	}

</script>

<style>
/*头部*/
.headSearch{
	position: relative;
	overflow: hidden;
}
.locate{
	width: 25%;
    float: left;
    display: inline-block;
}
.locateIcon{
	width: 1rem;
    height: 1rem;
    display: inline-block;
}
.innerSearch {
    float: right;
    width: 75%;
}
.innerSearch .mint-search {
    height: 100%;
}
.innerSearch .mint-searchbar{
    padding: 0;
}
.innerSearch .mint-searchbar-inner{
	padding: 0;
	/*background-color: #d0d0d0;*/
}
.innerSearch input{
	padding: 0;
    /*background-color: #d0d0d0;*/
}

/*.locate i.fa {
    width: 1rem;
    height: 1rem;
    display: inline-block;
    position: absolute;
    border: 1px solid;
    left: 2rem;
    top: 0;
}*/
/*.mint-searchbar-cancel{
	font-size: 0.8rem;
}
.mint-search{
	height: 100%;
	margin: 10px 0px 10px 50px;
}
.mint-searchbar{
    background-color: #E0E0E0;
    margin-left: 20px;
}
.mint-searchbar-inner{
}
.mint-searchbar-inner input{
    margin-left: 5px;	
}	*/

</style>