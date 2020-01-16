<template>
	<div>
		<div class="nav-gugger">
			<div>
				<ul class="nav-list">
					<li>
						<router-link to="/login"><img src="../assets/image/logo.png" width="60px" height="50px" alt=""></router-link>
					</li>
					<li class="nav-item">
						<router-link to="/home">首页</router-link>
					</li>
					<li class="nav-item">
						<router-link to="/explore">发现</router-link>
					</li>
					<li class="nav-item">
						<router-link to="/question/">等你来答</router-link>
					</li>
					<li class="nav-item1">
						<input type="text" height="50px" value="测试">
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
	.nav-list{
		width: 100%;
		margin: 0 auto;
		display: -webkit-box;
		padding:0;
		margin-left: 415px;
		height: 50px;
		text-decoration: none;
		
		
	}
	.nav-gugger{
		background-color: #ffffff;
		width:100%;
	}

	li{
		display: block;
		padding:0;
	}
	router-link{
		text-decoration: none;
	}
	.nav-item{
		font-size: 20px;
		margin-left: 18px;
		margin-right: 18px;
		margin-top: 13px;
	}
	.nav-item1{
		font-size: 20px;
		margin-left: 18px;
		margin-right: 18px;
		margin-top: 13px;
		border-width: 0;
	}

	.gutter{
		position: relative;
		margin-bottom: 10x;
	}
	
</style>
