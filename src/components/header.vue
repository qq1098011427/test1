<template>
	 <div id="header">
     <a class="h-text">水利工程建设全过程动态管理平台<span style="font-size:20px">——姚江上游西排工程</span></a>
      <div class="h-right">          
        <a class="icon1"></a>
        <a class="icon2"></a>
        <a class="icon3"></a>
        <a class="icon4"></a>
        <el-button icon="upload" style="border-radius:50%;"></el-button>
        <span style="font-size:20px">{{msg}}[xx_xxx]</span>
      </div>
   </div>
</template>

<script>
	export default{
		name:'',
		data(){
			return  {
				msg:'yxy'
			}
		}
	}
</script>

<style scoped>
#header{
background-color:#4480ef;
height:70px;line-height:70px;
font-size:25px;color:#fff;
font-family:Microsoft YaHei;
padding-left:30px;
}

.icon1{
  display:inline-block;
  width: 40px;
  height: 28px;
  background:url(../images/1.png) no-repeat;
}
.icon2{
   display:inline-block;
  width: 40px;
  height: 28px;
   background:url(../images/1.png) no-repeat -40px 0;
}
.icon3{
   display:inline-block;
  width: 40px;
  height: 28px;
   background:url(../images/1.png) no-repeat -80px 0;
}
.icon4{
  display:inline-block;
  width: 40px;
  height: 28px;
  background:url(../images/1.png) no-repeat -120px 0;
}
.h-right{
    float: right;
}

@media (max-width: 767px) {
  .h-text{
    display: none;
  }
}
</style>