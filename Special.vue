<template>

  <div>
	  <div class="container">
	  		  <div class="row" v-for="(item,index) in specials" :key="index">
	  			  <div class="col-4"><img :src="item.banner" alt=""></div>
	  			  <div class="col-8">
	  			  			  <h3>{{item.title}}</h3>
	  			  			  <p class="meta">{{item.updated}}更新,{{item.viewCount}}次浏览</p>
	  			  			  <p  class="introduction">{{item.introduction}}</p>
	  			  			  <span v-for="(section,index) in item.section" :key="index" class="section">
	  			  				  {{section.sectionTitle}}
	  			  			  </span>
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
	.container{
		background-color: #000000;
	}
</style>

