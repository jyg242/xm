<template>
    <div>
        <!-- 头部 -->
        <headerAll></headerAll>
        <Foot class="foot"/>
        
        <Swiper class="swiper"/>
        <div><p>配方查询</p></div>
        <Ask class="ask"/>
       
        <swiperAbc/>
        <!-- 轮播 -->
        
    </div>
</template>

<script>
import headerAll from '../components/header'
import Swiper from '../components/swiper'
import Ask from '../components/ask'
import Foot from '../components/foot'
import swiperAbc from '../components/swiper01'
    export default {
        components:{
            headerAll,
            Swiper,
            Ask,
            Foot,
            swiperAbc
        },
        mounted(){
            var _hmt = _hmt || [];
        (function() {
            var hm = document.createElement("script");
            hm.src = "https://hm.baidu.com/hm.js?719c3b365ad1f41dd0ea86a72d92fdcc";
            var s = document.getElementsByTagName("script")[0];
            s.parentNode.insertBefore(hm, s);
            console.log(s.parentNode.insertBefore(hm, s))
        })();
        }
    }
</script>

<style scoped>
.swiper{
    margin-top:10px;
    width: 80%;
    margin: 50px auto 0;
    /* height: 1000px; */
}
.ask{
    width: 80%;
    margin: 0 auto;
}
div>p{
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
.foot{
    margin-top: 30px;
}
</style>