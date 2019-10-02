<template>
<div>
<el-button type="primary" @click="dialogVisible = true">회원가입</el-button>
<el-dialog
  title="회원가입 양식"
  :visible.sync="dialogVisible"
  width="600px"
  :before-close="handleClose">
  <span>아래사항을 작성해 주세요.</span>
  <el-form :model="ruleForm" :rules="rules" ref="ruleForm" label-width="120px" class="demo-ruleForm">
  <el-form-item label="이메일" prop="email">
    <el-input v-model="ruleForm.email" type="email"></el-input>
  </el-form-item>
  <el-form-item label="닉네임" prop="name">
    <el-input v-model="ruleForm.name"></el-input>
  </el-form-item>
  <el-form-item label="패스워드" prop="password">
    <el-input v-model="ruleForm.password" type="password"></el-input>
  </el-form-item>
  <!-- <el-form-item label="Activity zone" prop="region">
    <el-select v-model="ruleForm.region" placeholder="Activity zone">
      <el-option label="Zone one" value="shanghai"></el-option>
      <el-option label="Zone two" value="beijing"></el-option>
    </el-select>
  </el-form-item>
  <el-form-item label="Activity time" required>
    <el-col :span="11">
      <el-form-item prop="date1">
        <el-date-picker type="date" placeholder="Pick a date" v-model="ruleForm.date1" style="width: 100%;"></el-date-picker>
      </el-form-item>
    </el-col>
    <el-col class="line" :span="2">-</el-col>
    <el-col :span="11">
      <el-form-item prop="date2">
        <el-time-picker placeholder="Pick a time" v-model="ruleForm.date2" style="width: 100%;"></el-time-picker>
      </el-form-item>
    </el-col>
  </el-form-item>
  <el-form-item label="Instant delivery" prop="delivery">
    <el-switch v-model="ruleForm.delivery"></el-switch>
  </el-form-item>
  <el-form-item label="Activity type" prop="type">
    <el-checkbox-group v-model="ruleForm.type">
      <el-checkbox label="Online activities" name="type"></el-checkbox>
      <el-checkbox label="Promotion activities" name="type"></el-checkbox>
      <el-checkbox label="Offline activities" name="type"></el-checkbox>
      <el-checkbox label="Simple brand exposure" name="type"></el-checkbox>
    </el-checkbox-group>
  </el-form-item>
  <el-form-item label="Resources" prop="resource">
    <el-radio-group v-model="ruleForm.resource">
      <el-radio label="Sponsorship"></el-radio>
      <el-radio label="Venue"></el-radio>
    </el-radio-group>
  </el-form-item>
  <el-form-item label="Activity form" prop="desc">
    <el-input type="textarea" v-model="ruleForm.desc"></el-input>
  </el-form-item> -->
  <el-form-item>
    <el-button type="primary" @click="submitForm('ruleForm')">회원가입 하기</el-button>
    <el-button @click="resetForm('ruleForm')">Reset</el-button>
  </el-form-item>
</el-form>

  <!-- <span slot="footer" class="dialog-footer">
    <el-button @click="dialogVisible = false">Cancel</el-button>
    <el-button type="primary" @click="dialogVisible = false">Confirm</el-button>
  </span> -->
</el-dialog>
</div>
</template>
<script>
  export default {
    data() {
      return {
        dialogVisible: false,
        ruleForm: {
          name: '',
          email: '',
          password: ''
          
        //   region: '',
        //   date1: '',
        //   date2: '',
        //   delivery: false,
        //   type: [],
        //   resource: '',
        //   desc: ''
        },
        rules: {
          name: [
            { required: true, message: '닉네임을 넣어주세요.', trigger: 'blur' },
            { min: 3, max: 20, message: '닉네임은 3글자에서 20글자 사이입니다.', trigger: 'blur' }
          ],
          email: [
            { required: true, message: '이메일을 넣어주세요.', trigger: 'blur' }
          ],
          password: [
            { required: true, message: '비밀번호을 넣어주세요.', trigger: 'blur' },
            { min: 3, max: 20, message: '비밀번호은 3글자에서 20글자 사이입니다.', trigger: 'blur' }
          ]
        //   ,
        //   region: [
        //     { required: true, message: 'Please select Activity zone', trigger: 'change' }
        //   ],
        //   date1: [
        //     { type: 'date', required: true, message: 'Please pick a date', trigger: 'change' }
        //   ],
        //   date2: [
        //     { type: 'date', required: true, message: 'Please pick a time', trigger: 'change' }
        //   ],
        //   type: [
        //     { type: 'array', required: true, message: 'Please select at least one activity type', trigger: 'change' }
        //   ],
        //   resource: [
        //     { required: true, message: 'Please select activity resource', trigger: 'change' }
        //   ],
        //   desc: [
        //     { required: true, message: 'Please input activity form', trigger: 'blur' }
        //   ]
        }
      };
    },
    methods: {
      submitForm(formName) {
        this.$refs[formName].validate((valid) => {
          if (valid) {
            alert('제출하였습니다!');
          } else {
            console.log('제출에 에러가 있습니다!!');
            return false;
          }
        });
      },
      resetForm(formName) {
        this.$refs[formName].resetFields();
      }
      //,
    //   handleClose(done) {
    //     this.$confirm('Are you sure to close this dialog?')
    //       .then(_ => {
    //         done();
    //       })
    //       .catch(_ => {});
    //   }
    }
  };


  
</script>