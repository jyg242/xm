<template>
    <div>
        <el-form :model="ruleForm2" status-icon :rules="rules2" ref="ruleForm2" label-width="100px" class="demo-ruleForm">
                <el-form-item label="真实姓名" prop="user">
                    <el-input type="text" v-model="ruleForm2.user" autocomplete="off"></el-input>
                </el-form-item>
                <el-form-item label="手机号码" prop="phone">
                    <el-input type="text" v-model="ruleForm2.phone" autocomplete="off"></el-input>
                </el-form-item>
                <!-- <el-form-item label="QQ号" prop="qq">
                    <el-input v-model.number="ruleForm2.qq"></el-input>
                </el-form-item> -->
                <el-form-item>
                    <el-button type="primary" @click="submitForm('ruleForm2')">提交</el-button>
                    <el-button @click="resetForm('ruleForm2')">重置</el-button>
                </el-form-item>
         </el-form>
        </div>
</template>

<script>
import axios from 'axios'
    export default {
        data() {
          return {
            ruleForm2: {
                // qq: '',
                phone: '',
                user: ''
            },
            rules2: {
                
                        user:[{
                            required:true,message:'请输入真实姓名',trigger:'blur'
                        }],
                        phone:[
                                { required: true, message: '请输入手机号', trigger: 'blur' },
                                { pattern: /^1[34578]\d{9}$/, message: '目前只支持中国大陆的手机号码' }
                        ],   
                        // qq: [
                        // { required: true, message: '请输入qq', trigger: 'blur' }],
                
            }
        };
    },
    methods: {
      submitForm(formName) {
        this.$refs[formName].validate(async (valid) => {
          if (valid) {
            
            let {status,data:{code,message}} = await axios.post('http://127.0.0.1:3000/user/register',{
                userName:this.ruleForm2.user,
                phone:this.ruleForm2.phone,
                // qq:this.ruleForm2.qq
            })
            // console.log(status,code,message)
            if(status===200&&code===200){
                await this.$alert('提交成功,请耐心等待')
                this.$router.go(0)
            }else{
                this.$alert('提交失败,姓名已存在,请修改后重新提交')
            }
          } else {
            this.$alert('无法提交,请填写正确信息')
            return false;
          }
        });
      },
      resetForm(formName) {
        this.$refs[formName].resetFields();
      }
    }
}
</script>

<style scoped>

</style>