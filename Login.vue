<template>
	<div class="login-bar tx-center">
		<!-- <router-link to="/">
			<img src="https://pic4.zhimg.com/100/v2-ce6afb652d5269a625392a197f07dca7_hd.png" class="logo" />
		</router-link> -->
	</div>
</template>

<script>
	export default{
		name:'login',
		data(){
			return{};
		},
		created() {}
	};
</script>

<style lang="scss" scoped>
	.login-bar{
		background-image: url(https://static.zhihu.com/heifetz/assets/sign_bg.db29b0fb.png);
		background-repeat: no-repeat;
		background-color: #b8e5f8;
		background-size: cover;
		width: 100%;
		height:63rem;
		overflow-x: hidden;
		overflow-y: hidden;
		.logo{
			width: 128px;
			height: 81px;
			margin-bottom: 24px;
			margin-top: 40px;
		}
	}
</style>
