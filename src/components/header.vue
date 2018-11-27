<template>
    <div class="containt">
        <vue-particles></vue-particles>
        <!-- header部分-->
        <div class="header">
            <div class="log">     
                <h1>化&nbsp;工&nbsp;类&nbsp;产&nbsp;品&nbsp;配&nbsp;方&nbsp;查&nbsp;询&nbsp;系&nbsp;统</h1>
            </div>
            <div class="input">
                <el-row>
                    <el-col :span='20'>
                        <el-input placeholder='输入配方名称查询' v-model="searchName" id="serach-1"></el-input>
                    </el-col>
                    <el-col :span='4'><el-button class='hs' type='primary' @click="abc()">立即获取</el-button></el-col>
                </el-row>
            </div>
            <!-- 注册对话框 -->
            <!-- Form -->
            <div class="register">
                <el-dialog title="配方查询" :visible.sync="dialogFormVisible">
                    <FormCom/>
                </el-dialog>
            </div>    
            <div class="hotSearch">
                <label><i class="iconfont"></i>热搜词：</label><p>
                <span>胶黏剂配方</span>
                <span>免擦拭洗车液配方</span>
                <span>切削液配方</span>
                <span>塑料稳定剂配方</span>
                <span>光学玻璃清洗剂配方</span>
                <span>亚克力胶水配方</span>
                <span>漆雾凝聚剂配方</span>
                <span>丙烯酸乳液配方</span>
                <span>铬酸洗液配方</span>
                <span>喷码机油墨配方</span>
                <span>弱溶剂油墨配方</span>
                <span>食品防腐剂配方</span>
                <span>环保催化剂配方</span></p>
                
            </div>
            <el-row class="nav">
                <el-col>
                    <h2>胶黏剂配方</h2>
                    <p>相同或不同物料连接或贴合的各种应力材料总称。主要有液态、膏状和固态三种类型</p>
                    <el-button type='danger' @click="register">点击查询</el-button>
                </el-col>
                <el-col>
                    <h2>免擦拭洗车液配方</h2>
                    <p>通过将专用免擦拭洗车产品用清水按配比溶解后，形成含护理成分活性液体——免擦拭清洗液</p>
                    <el-button type='danger' @click="register">点击查询</el-button>
                </el-col>
                <el-col>
                    <h2>切削液配方</h2>
                    <p>由多种超强功能助剂经科学复合配合而成，同时具备良好的冷却性能、润滑性能、防锈性能、除油清洗功能、防腐功能、易稀释特点。</p>
                    <el-button type='danger' @click="register">点击查询</el-button>
                </el-col>
                <el-col>
                    <h2>塑料稳定剂配方</h2>
                    <p>有效地阻止、减少甚至基本停止材料的降解</p>
                    <el-button type='danger' @click="register">点击查询</el-button>
                </el-col>
            </el-row>
        </div>
    </div>
</template>

<script>
import FormCom from '../components/form'
    export default {
        data() {
            return {
                searchName:'',
                dialogFormVisible: false,
                form: {
                name: '',
                phone: '',
                qq: '',
                },
                formLabelWidth: '120px'
            };
        },
        methods: {
            abc(){
                if(!this.searchName){
                    this.$message.error('输入需要查询的配方')
                    }else{
                       this. dialogFormVisible=true
                    }
            },
            register(){
                this. dialogFormVisible=true
            }
        },
        components:{
            FormCom
        }
  }
    
</script>

<style scoped>

.containt{
 /* background: linear-gradient(top,#0f67b3,#fff);
  */
 background: rgb(17, 18, 33);
 height: 100%;
 position: relative;
}
.header{ 
    padding-top: 145px;
    width: 1038px;  
    height: 712px;  
    margin: 0px auto 0;
    margin-top: -55%;
}
.log{
    margin-bottom: 80px;
}
.log h1{
    font-size: 54px;
    line-height: 46px;
    color: #fff;
    font-weight: bold;
}
.input{
    margin: 50px 150px;
    height: 60px;
}
#serach-1{
    border-color:red;
} 
.hs{
    float: right;
    
}
.hotSearch{
    padding-left: 90px;
    position: relative;
    word-wrap:break-word;
    margin-top: 5%;
    

}
.hotSearch p{
    text-align: left;
}
.hotSearch label{
    position: absolute;
    left: 0;
    top: 0;
    font-size: 16px;
    line-height: 20px;
    color: #c5e2ff;
}
.hotSearch span{    
    font-size: 16px;
    line-height: 20px;
    color: #c5e2ff;
    margin-bottom: 5px;
    margin-right: 12px;}
.nav{
    height:186px;
    margin: 10% 0 0 0;
    /* border: 1px solid red; */
    padding: 25px 0;
    display: flex;
    justify-content: space-between;
    flex: 1;
    background-color: #2381D0;
}
.nav div{
    padding: 10px 10px;
    border-right:1px dashed #fff;
   
}
.nav div:last-child{

    border-right:none;
}
.nav div h2{
    font-size: 24px;
    line-height: 26px;
    color: #fff;
    font-weight: bold;
}
.nav div p{
    height: 60px;
    font-size: 14px;
    line-height: 30px;
    margin-top: 5px;
    color: #fff;
    word-break: break-all;
    text-overflow: ellipsis;
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: 2;
    overflow: hidden;
    /* margin: 10px 0 20px 0; */
}
/* 轮播图
 */
 .header{
     z-index: 100;
 }
</style>