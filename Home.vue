<template>
  <div>
	 
	 <div class="container">
		  <div class="row" v-for="(item,index) in specials" :key="index">
			  <div class="col-4">
				  <h3>{{item.title}}</h3>
				  <div class="col-6">
					  <img :src="item.banner" width="195px" height="105px" alt="">
					  <textarea name="" id="" cols="40" rows="11" readonly="readonly" class="introduction" onchange="this.value=this.value.substring(0, 20)" onkeydown="this.value=this.value.substring(0, 20)" onkeyup="this.value=this.value.substring(0, 20)">{{item.introduction}}</textarea>
				  </div>
				  <div class="col-8">
					  <p class="meta">{{item.updated}}更新,{{item.viewCount}}次浏览</p>
					  <span v-for="(section,index) in item.section" :key="index" class="section">
						  {{section.sectionTitle}}
					  </span>
				  </div>
			   </div>
			  
		  </div>
		  
	  </div>
  </div>
</template>

<script>
	export default{
		name:'specials',
		data(){
			return{
				specials:[]
			};
		},
		created(){
			this.axios.get('http://localhost:8081/api/special/all').then(res =>{
				console.log(res);
				this.specials = res.data.data;
			})
		}
	}
</script>
<style lang="scss" scoped>
	.meta{
		margin-left: 1.5625rem;
		margin-right: 1.5625rem;
	}
	.row{
		border-style: solid;
		border-width:0.01rem;
		width: 100%;
	}
	.introduction{
		width: 320px;
		height: 105px;
		font-size: 15px;
		background-color: #f6f6f6;
		cursor:pointer;
		BORDER-BOTTOM: 0px solid;
		BORDER-LEFT: 0px solid; 
		BORDER-RIGHT: 0px solid; 
		BORDER-TOP: 0px solid;
	}
	.vanner{
		width:100%;
	}
	.col-4{
		width: 100%;
		text-decoration: none;
		
		
		
	}
	.container{
		margin-top: 10px;
		margin-left: 50px;
		width: 600px;
	}
	.col-6{
		display: -webkit-box;
		height: 120px;
		border-width: 0;
		cursor:pointer;
		margin-left: 0.0625rem;
		
	}
</style>

