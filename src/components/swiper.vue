<template>

        <div class="swiper">
           
            <p>配方展示</p>
            <template>
                <el-carousel :interval="5000" type="card" height="450px">
                    <el-carousel-item v-for="(item,index) in swiper" :key="index">
                        <img :src=item.src alt="" width="100%" height="100%">
                    </el-carousel-item>
                </el-carousel>
            </template>   
        </div>  
</template>

<script>

    export default {
        data() {
            return {
                swiper: [{src:require('../assets/1.jpg')},{src:require('../assets/2.jpg')},{src:require('../assets/3.jpg')},{src:require('../assets/4.jpg')},{src:require('../assets/5.jpg')}]
            }
        },
       
    }
</script>

<style scoped>
  .el-carousel__item h3 {
    color: #475669;
    font-size: 14px;
    opacity: 0.75;
    line-height: 200px;
    margin: 0;
  }
  
   .el-carousel__item:nth-child(2n) {
    background-color: #99a9bf;
  }
  
  .el-carousel__item:nth-child(2n+1) {
    background-color: #d3dce6;
  }
  p{
    /* font-size: 30px;
    font-weight: normal;
    text-align: center;
    margin-top: 70px;
    line-height: 150%;
    font-family: PingFangSC-Regular, Microsoft Yahei, arial, Hiragino Sans GB;
    margin-bottom: 35px; */
    height: 126px;
    background: url(https://www.mingdada.com/assets/img/3.0/0_zi_3@2x.png) top center no-repeat;
    background-size: 874px 126px;
    color: #2ea8e6;
    text-align: 126px;
    line-height: 166px;
    font-family: PingFangSC-Regular, Microsoft Yahei, arial, Hiragino Sans GB;
    margin-bottom: 70px;
     font-size: 30px;

  }
</style>