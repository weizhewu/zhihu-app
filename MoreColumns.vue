<template>
   <div class="body">
	   <div class="more-head">
		   <ul >
			  <li style="list-style-type: none">专栏</li>
			  <li >发现</li>
			  
		  </ul>
	   </div>
        <div class="content">
   		 <div class="card" v-for="(moreColumn,index) in moreColumns.slice(0,8)" :key="index">
   			 <div class="card-header">
   				 <div class="avatar">
   					 <img :src="moreColumn.imageUrl" alt="头像">
   				 </div>
   			 </div>
   			 <div class="card-body">
   				 <div  class="card-title" >
   					 <a href="">{{ moreColumn.title  }}</a>
   				 </div>
   				 <div class="card-info">
   					 {{ moreColumn.description }}
   				 </div>
   				 <div class="count">
   					 <span class="count-span">{{ moreColumn.followers}}关注</span><span class="count-span">{{ moreColumn.articlesCount}}文章</span>
   				 </div>
   				 <div class="card-button">
   					 <input type="button" value="进入专栏">
   				 </div>
   			 </div>
        
        </div>
     
   	</div>
   
   </div>
</template>

<script>
    export default {
        name: "MoreColumns",
        data(){
            return{
                moreColumns:[],


            }
        },
        created() {
            this.axios.get('http://localhost:8081/api/columns/all').then( res =>{
                console.log(res)
                this.moreColumns = res.data.data
            })

        },
        methods: {
            getMore(){
               this.moreColumns.slice(8,7)
            }
        }
    }
</script>

<style lang="scss" scoped>
 @import url("../assets/css/basic.css");
   @import url("../assets/css/style.css");
#more-columns{
    width: 100%;
    height: 100%;
    margin: 0 auto;
}
.more-head{
	margin-left: 550px;
	height: 30px;
	display: flex;
	color: #1a1a1a;
	font-size: 14px;
	font-weight: 600;
	text-align: center;
	padding-bottom: 15px;
	margin-top: 20px;
	ul{
		margin-top: 200px;
		display: flex;
	   padding-left: 150px;
		li:last-child{
			margin-left: 30px;
		}
	}
}
 .body{
        width:100%;
       height: 2000px;
        background: #eee;
    }
    .content{
        margin:180px 260px;
        padding: 0 30px;
        width: 1000px;
        background:#eee;
        text-align: center;
        .card{
            margin-top: 20px;
            text-align: center;
            padding: 28px 24px;
            box-sizing: border-box;
            width: 206px;
            height: 264px;
            border-radius: 4px;
            -webkit-box-shadow: 0 1px 3px 0 rgba(26,26,26,.1);
            box-shadow: 0 1px 3px 0
            rgba(26,26,26,.1);
            background-color: #fff;
            margin-left: 20px;
            float: left;
            .card-header{
                text-align: center;
                .avatar {
                    width: 48px;
                    height: 48px;
                    margin: 0 auto;

                    img {
                        border-radius: 50%;
                        width: 100%;
                        height: 100%;
                    }
                }
            }
            .card-body{
                width: 100%;
                .card-title{
                    margin-top:10px;
                    height: 22px;
                    line-height: 22px;
                    font-size: 16px;
                    max-width: 187px;
                    white-space: nowrap;
                    overflow: hidden;
                    text-overflow: ellipsis;
                    font-weight: 600;
                    font-synthesis: style;
                    text-align: center;
                    a{
                        color: inherit;
                        text-decoration: none;
                    }

                }
                .count{
                    margin-top: 4px;
                    height: 17px;
                    line-height:17px;
                    color: grey;
                    font-size: 14px;
                    margin-top: 14px;
                    span:first-child{
                        padding-right: 4px;
                        border-right: 1.3px solid gray;
                    }
                    .count-span{

                    }
                }
                .card-info{
                    margin-top: 7px;
                    height: 40px;
                    line-height: 21px;
                    color: grey;
                    font-size: 14px;
                    text-align: center;
                    display: -webkit-box;
                    overflow: hidden;
                    text-overflow: ellipsis;
                }
                .card-button{
                    input[type=button]{
                        color: #11a668;
                        display: inline-block;
                        padding: 0 16px;
                        font-size: 14px;
                        line-height: 32px;
                        cursor: pointer;
                        background: none;
                        border: 1px solid #11a668 ;
                        border-radius: 3px;
                        outline: none;
                        margin-top: 15px;
                    }
                }

            }

        }

    }

</style>
