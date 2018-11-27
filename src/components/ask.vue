<template>
    <div class="contant">
        <el-row class="wa">
            <el-col :span='12' class="left">
                <FormCom/>
            </el-col>
            <el-col :span='12' class="right">
                <img src="../assets/timg.jpeg" alt="" width="60%">
            </el-col>
        </el-row>
    </div>
</template>

<script>
import FormCom from '../components/form'
  export default {
    components:{
        FormCom
    }
  }
</script>


<style scoped>
.contant{
    border: 1px solid #2ea8e6;
    /* display: flex;
    flex-direction: row;
    justify-content:space-around;
    align-items: center;
     */
    /* padding-top: 50px; */
    /* padding-right: 550px;
    box-sizing: border-box; */
}

.left{
    padding-top: 50px;
}
/* .right{
    display: flex;
    align-items: center;
    justify-content: center;
} */
.wa{
    display: flex;
    align-items: center;
    justify-content: center;}

</style>