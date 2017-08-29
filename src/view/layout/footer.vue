<template>
		<div class="footer">
		  	<mt-tabbar>
		  	  	<mt-tab-item>
			  	    <router-link to="/seek">
						<i class="fa fa-hospital-o" aria-hidden="true"></i>
						<span>就医</span>
			  	  	</router-link> 
		  	  	</mt-tab-item>
		  	  	<mt-tab-item>
			  	    <router-link to="/health">
						<i class="fa fa-heart-o" aria-hidden="true"></i>
						<span>健康</span>
			  	  	</router-link> 
		  	  	</mt-tab-item>
		  	  	<mt-tab-item>
			  	    <router-link to="/chat">
						<i class="fa fa-comments-o" aria-hidden="true"></i>
						<span>互动</span>
			  	  	</router-link> 
		  	  	</mt-tab-item>
		  	  	<mt-tab-item>
			  	    <router-link to="/mine">
						<i class="fa fa-user" aria-hidden="true"></i>
						<span>我的</span>
			  	  	</router-link> 
		  	  	</mt-tab-item>
		  	</mt-tabbar>
		</div>
</template>

<script>

	export default {
		
		data(){
			return{

			}
		}
	}
</script>

<style>
/*尾部*/
.footer{
	height: 4rem;
    margin-top: .9rem;
    position: relative;
}
.mint-tabbar{
	position: fixed;
}
.footer i{
	display: block;
    margin-bottom: .9rem;
    font-size: 1.3rem;

}
/*.footer span{
}*/
.footer .mint-tabbar > .mint-tab-item.is-selected{
	
	text-decoration: none;
}

.footer .mint-tab-item-label{
	
}	
</style>