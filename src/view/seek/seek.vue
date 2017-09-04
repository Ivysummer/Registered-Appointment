<template>
	<div class="seek">
		<!-- 就医 -->
		<div class="con">
		    <!-- 轮播图 -->
			<div class="swipe_bar">
				<mt-swipe :auto="4000">
				  <mt-swipe-item><img src="../../assets/swipe1.jpg"></mt-swipe-item>
				  <mt-swipe-item><img src="../../assets/swipe2.jpg"></mt-swipe-item>
				  <mt-swipe-item><img src="../../assets/swipe3.jpg"></mt-swipe-item>
				</mt-swipe>
			</div>
			<!-- 相关服务 -->
	    	<ul class="service_nav">
	    		<li v-for="item in serListsTypes">
	    			<figure>
	    				<img :src="item.image_url">
	    				<figcaption>{{ item.title }}</figcaption>
	    			</figure>
	    			
	    		</li>
	    	</ul>
	    	<!-- 资讯 -->
			<div class="news">
				<p>资讯</p>
				<div class="msg-tab">
					<mt-navbar v-model="msgSelected">
					  <mt-tab-item id="recommend">推荐</mt-tab-item>
					  <mt-tab-item id="health">保健</mt-tab-item>
					  <mt-tab-item id="diet">饮食</mt-tab-item>
					  <mt-tab-item id="doctor">中医</mt-tab-item>
					  <mt-tab-item id="old">老人</mt-tab-item>
					  <button><i class="fa fa-plus" aria-hidden="true"></i></button>
					</mt-navbar>

					<!-- tab-container -->
					<mt-tab-container v-model="msgSelected">
					<!-- 推荐 -->
					  <mt-tab-container-item id="recommend">
					    <!-- <mt-cell v-for="n in 10" :title="'content ' + n" /> -->
					    <ul class="recommendList">
					    	<li v-for="item in recommendList">
					    		<hgroup>
					    			<p>{{ item.title }}</p>
					    			<span>{{ item.conut }}赞</span>
					    		</hgroup>
					    		<section>
					    			<img slot="icon" :src="require(`../../assets${item.image_url}`)" width="60" height="60">
					    		</section>
					    		
					    	</li>
					    </ul>
					  </mt-tab-container-item>
					  <!-- 保健 -->
					  <mt-tab-container-item id="health">
					    <ul class="healthList">
					    	<li v-for="(item,index) in healthList">
					    		<div class="healthSpecial" v-if="index==0 ||index == 3">
					    			<hgroup>
					    				<p> {{ item.title }} </p>
					    				<img slot="icon" :src="require(`../../assets${item.image_url}`)" width="60" height="60">	
					    			</hgroup>
					    			<section>
					    				<span>{{ item.conut }}赞</span>
					    			</section>
					    		</div>
					    		<div class="others" v-else>
					    			<hgroup>
					    				<p>{{ item.title }}</p>
					    				<span>{{ item.conut }}赞</span>
					    			</hgroup>
					    			<section>
					    				<img slot="icon" :src="require(`../../assets${item.image_url}`)" width="60" height="60">
					    			</section>
					    		</div>
					    		
					    	</li>
					    </ul>
					  </mt-tab-container-item>
					  <!-- 饮食 -->
					  <mt-tab-container-item id="diet">
					    <ul class="dietList">
					    	<li v-for="item in dietList">
					    		<hgroup>
					    			<p>{{ item.title }}</p>
					    			<span>{{ item.conut }}赞</span>
					    		</hgroup>
					    		<section>
					    			<img slot="icon" :src="require(`../../assets${item.image_url}`)" width="60" height="60">
					    		</section>
					    		
					    	</li>
					    </ul>
					  </mt-tab-container-item>
					  <!-- 中医 -->
					   <mt-tab-container-item id="doctor">
					    <ul class="doctorList">
					    	<li v-for="(item,index) in doctorList">
					    		<div class="doctorSpecial" v-if="index == 3">
					    			<hgroup>
					    				<p> {{ item.title }} </p>
					    				<img slot="icon" :src="require(`../../assets${item.image_url}`)" width="60" height="60">
					    			</hgroup>
					    			<section>
					    				<span>{{ item.conut }}赞</span>
					    			</section>
					    		</div>
					    		<!-- 展示一列图片（未实现） -->
					    		<!-- <div class="another" v-else-if="index == 1">
					    			<hgroup>
					    				<p> {{ item.title }} </p>
					    				<div class="groupImg" v-for="arr in doctorList.arrayImg">
					    					<img :src="item.arr.image_url">
					    				</div>
					    			</hgroup>
					    			<section>
					    				<span>{{ item.conut }}赞</span>
					    			</section>
					    		</div> -->
					    		<div class="others" v-else>
					    			<hgroup>
					    				<p>{{ item.title }}</p>
					    				<span>{{ item.conut }}赞</span>
					    			</hgroup>
					    			<section>
					    				<img slot="icon" :src="require(`../../assets${item.image_url}`)" width="60" height="60">
					    			</section>
					    		</div>
					    		
					    	</li>
					    </ul>

					  </mt-tab-container-item>
					  <!-- 老人 -->
					   <mt-tab-container-item id="old">
					    <ul class="oldList">
					    	<li v-for="(item,index) in oldList">
					    		<div class="oldSpecial" v-if="index == 3 || index == 7">
					    			<hgroup>
					    				<p> {{ item.title }} </p>
					    				<img slot="icon" :src="require(`../../assets${item.image_url}`)" width="60" height="60">
					    			</hgroup>
					    			<section>
					    				<span>{{ item.conut }}赞</span>
					    			</section>
					    		</div>
					    		<!-- 展示一列图片（未实现） -->
					    		<!-- <div class="another" v-else-if="index == 1">
					    			<hgroup>
					    				<p> {{ item.title }} </p>
					    				<div class="groupImg" v-for="arr in doctorList.arrayImg">
					    					<img :src="item.arr.image_url">
					    				</div>
					    			</hgroup>
					    			<section>
					    				<span>{{ item.conut }}赞</span>
					    			</section>
					    		</div> -->
					    		<div class="noImg" v-else-if="index == 2" >
					    			<hgroup>
					    				<p>{{ item.title }}</p>
					    				
					    			</hgroup>
					    			<section>
					    				<span>{{ item.conut }}赞</span>
					    			</section>
					    		</div>
					    		<div class="others" v-else>
					    			<hgroup>
					    				<p>{{ item.title }}</p>
					    				<span>{{ item.conut }}赞</span>
					    			</hgroup>
					    			<section>
					    				<img slot="icon" :src="require(`../../assets${item.image_url}`)" width="60" height="60">
					    			</section>
					    		</div>
					    		
					    	</li>
					    </ul>

					  </mt-tab-container-item>
					</mt-tab-container>
				</div>
			</div>
		</div>
	</div>
</template>

<script>

	const arrayImg = ["dietImg2","dietImg3","dietImg4"];
	export default {

		data(){
			return{
				value:'',
				serListsTypes:null,// 中间 相关服务列表
				selected: "就医",				
				msgSelected: "recommend",//资讯				
				recommendList:null,// 推荐列表
				healthList:null,//保健列表				
				dietList:null,//饮食列表
				doctorList:null,// 中医列表				
				oldList:null,//老人列表

			}
		},
		//一进来就展示   记得要调用
		mounted:function(){
		 var vm=this;
		 vm.getData();//获取JSON数据
		},
		methods:{
			//获取动态数据（json也有可能接口）
			getData(){
			var vm = this;	
			 vm.$http.get('../../../static/dataJson/seekInfo.json').then(function(response){
			   // alert(1);
			   console.log("这是我们需要的json数据",response.data.data)//返回所有的数据
			   vm.recommendList = response.data.data.recommendList;// 推荐列表
			   vm.healthList = response.data.data.healthList;      // 保健列表
			   vm.dietList = response.data.data.dietList;          // 饮食列表
			   vm.doctorList = response.data.data.doctorList;      // 中医列表
			   vm.oldList = response.data.data.oldList;           // 老人列表
			 }, function(response){
			   alert("请求失败了")
			 })
			}

		}
	}
	
</script>

<style scoped>
/*中间*/
.con{
	position: relative;
}
.swipe_bar{
	position: relative;
    width: 100%;
    height: 10rem;
    margin-bottom: .3rem;
}
.swipe_bar img{
	width: 24rem;
    height: 10rem;
}
ul.service_nav{
	margin: 0;
	padding: 0;
	list-style: none;
	width: 100%;
	overflow: hidden;
	font-size: 0.5rem;
}
li{
	float: left;
    width: 33%;
    display: flex;
    justify-content: center;
    padding: .4rem 0;
}
li img{
	width: 3.2rem;
    height: 3.2rem;
    border-radius: 50%;
    border: 1px solid #fff;
    margin-bottom: .3rem;
}
.figcaption{
	color: #5B5B5B;
}
/*资讯*/
.news > p {
    text-align: left;
    margin-left: .8rem;
    margin: .5rem auto;
    font-size: .8rem;
}
.mint-navbar{
	border-bottom: 1px solid #e1e1e1;
}
.mint-navbar button{
	background-color: #fff;
    border-width: 0;
    border-color: #fff;
    outline-color: #fff;
    color:#2894FF;
}
.msg-tab .mint-navbar > .mint-tab-item.is-selected{
	color: #26a2ff;
}
/*推荐*/
 ul.recommendList {
    background-color: #fff;
    overflow: hidden;
    margin: 0;
    padding: 0;
}
ul.recommendList li{
	width: 100%;
	border-bottom: 1px solid #e1e1e1;
}
hgroup{
    text-align: left;
    width: 70%;
}
hgroup p{
    font-size: .7rem;
    color: #272727;
    font-weight: 600;
    font-family: inherit;
    margin: 5px 0;
}
hgroup span{
	font-size: .2rem;
}
section{
    margin-left: 2rem;

}
section img {
    width: 4.2rem;
    height: 3.5rem;
    border-radius: 30%;
}
/*保健*/
 ul.healthList {
    background-color: #fff;
    overflow: hidden;
    margin: 0;
    padding: 0;
}
ul.healthList li{
	width: 100%;
	border-bottom: 1px solid #e1e1e1;
}
ul.healthList li section img {
    width: 4.2rem;
    height: 3.5rem;
    border-radius: 0;
}
.others{
	display: inherit;
    width: 100%;
}
/*保健 v-if 样式*/
.healthSpecial{
	width: 100%;
    margin-bottom: 0.8rem;
}
.healthList .healthSpecial hgroup {
    width: 100%;
    height: 12rem;
    overflow: hidden;
    margin-bottom: 1rem;
}

.healthSpecial hgroup img {
    border-radius: 0;
    width: 100%;
    height: 100%;
}
.healthSpecial section{
	margin-left: 0;
    overflow: hidden;
    
}
.healthSpecial section span {
    font-size: .2rem;
    float: left;
}
/*饮食*/
ul.dietList {
    background-color: #fff;
    overflow: hidden;
    margin: 0;
    padding: 0;
}
ul.dietList li{
	width: 100%;
	border-bottom: 1px solid #e1e1e1;
}
/*中医*/
 ul.doctorList {
    background-color: #fff;
    overflow: hidden;
    margin: 0;
    padding: 0;
}
ul.doctorList li{
	width: 100%;
	border-bottom: 1px solid #e1e1e1;
}
ul.doctorList li section img {
    width: 4.2rem;
    height: 3.5rem;
    border-radius: 0;
}
.others{
	display: inherit;
    width: 100%;
}
/*中医 v-if 样式*/
.doctorSpecial{
	width: 100%;
    margin-bottom: 0.8rem;
}
.doctorList .doctorSpecial hgroup {
    width: 100%;
    height: 12rem;
    overflow: hidden;
    margin-bottom: 1rem;
}

.doctorSpecial hgroup img {
    border-radius: 0;
    width: 100%;
    height: 100%;
}
.doctorSpecial section{
	margin-left: 0;
    overflow: hidden;
    
}
.doctorSpecial section span {
    font-size: .2rem;
    float: left;
}

/*中医 v-else-if 样式*/
.another{
	width: 100%;
    margin-bottom: 0.8rem;
}
.doctorList .another hgroup {
    width: 100%;
    height: 12rem;
    overflow: hidden;
    margin-bottom: 1rem;
}

.another hgroup img {
    border-radius: 0;
    width: 100%;
    height: 100%;
}
.another section{
	margin-left: 0;
    overflow: hidden;
    
}
.another section span {
    font-size: .2rem;
    float: left;
}
/*老人*/
 ul.oldList {
    background-color: #fff;
    overflow: hidden;
    margin: 0;
    padding: 0;
}
ul.oldList li{
	width: 100%;
	border-bottom: 1px solid #e1e1e1;
}
ul.oldList li section img {
    width: 4.2rem;
    height: 3.5rem;
    border-radius: 0;
}
.others{
	display: inherit;
    width: 100%;
}
/*老人 v-if 样式*/
.oldSpecial{
	width: 100%;
    margin-bottom: 0.8rem;
}
.oldList .oldSpecial hgroup {
    width: 100%;
    height: 12rem;
    overflow: hidden;
    margin-bottom: 1rem;
}

.oldSpecial hgroup img {
    border-radius: 0;
    width: 100%;
    height: 100%;
}
.oldSpecial section{
	margin-left: 0;
    overflow: hidden;
    
}
.oldSpecial section span {
    font-size: .2rem;
    float: left;
}
/*老人 v-else-if 样式*/
.another{
	width: 100%;
    margin-bottom: 0.8rem;
}
.oldList .another hgroup {
    width: 100%;
    height: 12rem;
    overflow: hidden;
    margin-bottom: 1rem;
}

.another hgroup img {
    border-radius: 0;
    width: 100%;
    height: 100%;
}
.another section{
	margin-left: 0;
    overflow: hidden;
    
}
.another section span {
    font-size: .2rem;
    float: left;
}
/*老人 v-else-if 样式*/
.noImg{
	width: 100%;
    margin-bottom: 0.8rem;
}
.oldList .noImg hgroup {
    margin-bottom: 2rem;
}
.noImg section{
	margin: 0;
    overflow: hidden;
    
}
.noImg section span {
    float: left;
    font-size: .2rem;
}	

</style>