<template class="nav-body">
	<div class="nav-content">
		<div class="nav-gugger">
			<div class="nav-body">
				<ul class="nav-list">
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
			</div>
		</div>
		<!-- 二级路由入口 -->
		<router-view/>
	</div>
</template>

<script>
	export default{
		name:'Nav',
		data(){
			return {};
		},
		created() {}
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
		
	}
	.nav-list{
		
		margin: 0 auto;
		display: -webkit-box;
		padding:0;
		margin-left: 415px;
		height: 50px;
		
		
	}
	.nav-gugger{
		margin-top: 0;
		height: 9.6875rem;
		background-color: #F6F6F6;
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
		
	}
	.head{
		font-size: 16px;
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
