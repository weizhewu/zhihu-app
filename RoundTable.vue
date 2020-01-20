<template>
	<div class="body">
		<div v-for="(roundTable,index) in roundTables" :key="index" class="roundTable">
			<div class="col4">
				<img :src="roundTable.banner" alt="" class="img1">
				<h3>该圆桌被浏览{{roundTable.visitsCount}}次</h3>
			</div>
		</div>
	</div>
</template>

<script>
	export default{
		name:'roundTables',
		data(){
			return{
				roundTables:[]
			};
		},
		created(){
			this.axios.get('http://localhost:8081/api/roundTable/all').then(res =>{
				console.log(res);
				this.roundTables = res.data.data;
			})
			
		}
	}
</script>
	
<style>
	h3{
		font-size: 13px;
		color: #999999;
	}
	.img1{
		width: 12.5rem;
		height: 12.5rem;
		
	}
	.col4{
		float: left;
		margin-right: 25px;
	}
	.roundTable{
		width: 1000px;
		margin-left: 450px;
		display: block;
		margin-top: 1px;
		background-color: #FFFFFF
		
	}
	
</style>
