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
    position: fixed;
    width: 100%;
    right: 0;
    bottom: 0;
    left: 0;
}
.footer .mint-tabbar{
	position: fixed;
}
.footer i{
	display: block;
    margin-bottom: .9rem;
    font-size: 1.3rem;

}

.footer .mint-tab-item-label{
    display: block;
	
}
.footer .mint-tab-item-label a{
	color: #272727;
    text-decoration: none;
	cursor: none;
}
.footer .mint-tab-item-label a:hover{
	color:#26a2ff;
    

}	
</style>