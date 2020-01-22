<template class="nav-body">
	<div class="nav-content">
		<div class="nav-gugger">
			<div class="nav-body">
				<ul class="nav-list" id="searchBar">
					<li class="nav-title">
						<router-link to="/home" class="title">知乎</router-link>
					</li>
					<li class="nav-item">
						<router-link to="/home" class="head">首页</router-link>
					</li>
					<li class="nav-item">
						<router-link to="/explore" class="head">发现</router-link>
					</li>
					<li class="nav-item">
						<router-link to="/question/" class="head">等你来答</router-link>
					</li>
					<li class="nav-item1">
						<input type="text" height="50px" value="测试" class="nav-input">
					</li>
					<li class="search-img">
						<img src="../assets/image/search.png" class="nav-search-img" alt="">
					</li>
					
				</ul>
				<ul class="nav-list-1" id="searchBar1">
					<li class="nav-title">
						<router-link to="/home" class="title">知乎</router-link>
					</li>
					<li class="nav-item">
						<router-link to="/home" class="head">最新专题</router-link>
					</li>
					<li class="nav-item">
						<router-link to="/explore" class="head">圆桌讨论</router-link>
					</li>
					<li class="nav-item">
						<router-link to="/question/" class="head">热门收藏夹</router-link>
					</li>
					<li class="nav-item">
						<router-link to="/question/" class="head">专栏</router-link>
					</li>
					
					
				</ul>
			</div>
		</div>
		<!-- 二级路由入口 -->
		<router-view/>
	</div>
</template>

<script>
	export default{
		mounted () {
		  window.addEventListener('scroll', this.handleScroll)
		},
		
		methods: {
		  handleScroll () { 
			  // var scrollTop =  document.documentElement.scrollHeight || document.body.scrollHeight;
			  
		    var scrollTop = window.pageYOffset || document.documentElement.scrollTop || document.body.scrollTop;		
		    if(scrollTop>20){
		      document.querySelector('#searchBar').style.display ='none';
			  document.querySelector('#searchBar1').style.display = '-webkit-box';
		    }else{
				document.querySelector('#searchBar1').style.display ='none';
				document.querySelector('#searchBar').style.display = '-webkit-box';
			}
			
		  },
		},
		destroyed () {
		  window.removeEventListener('scroll', this.handleScroll)
		}
	
	}
	
</script>

<style lang="scss" scoped>
	.nav-search-img{
		width: 21px;
		height: 32px;
		
	}
	.nav-content{
		margin-top: 0;
		padding-top: 0;
		
	}
	.search-img{
		height: 32px;
		cursor:pointer;
		margin-top: 8px;
		background-color: #F6F6F6;
		
	}
	router-link{
		background-color: #f6f6f6;
	}
	.nav-body{
		background-color: #FFFFFF;
		overflow-x: hidden;
		position: fixed;
		width: 100%;
		
		
	}
	.nav-list{
		margin: 0 auto;
		display: -webkit-box;
		padding:0;
		margin-left: 415px;
		height: 50px;
		margin-top: 1px;
		position: fixed;
		
		
		
	}
	.nav-list-1{
		margin: 0 auto;
		display: none;
		padding:0;
		margin-left: 415px;
		height: 50px;
		margin-top: 1px;
		position: fixed;
		
		
		
		
	}
	.nav-gugger{
		margin-top: 0;
		height: 50px;
		background-color: #FFFFFF;
	}

	li{
		display: block;
		padding:0;
	}
	router-link{
		text-decoration: none;
		font-size: 10px;
	}
	.title{
		font-size: 30px;
		color: #0084ff;
		text-decoration: none;
		
	}
	.head{
		font-size: 16px;
		text-decoration: none;
	}
	.nav-item{
		margin-left: 18px;
		margin-right: 18px;
		margin-top: 14px;
		font-size: 5px;
	}
	
	.nav-title{
		margin-left: 18px;
		margin-right: 18px;
		margin-top: 2px;
	}
	
	.nav-item1{
		margin-top: 8px;
	}
	.nav-input{
		height: 30px;
		width: 300px;
		margin-right: 0px;
		background-color: #F6F6F6;
		border-width: 0;
		border-radius: 1px;
		color: #55557f;
	}

	.gutter{
		position: relative;
		margin-bottom: 10x;
	}
	
</style>
