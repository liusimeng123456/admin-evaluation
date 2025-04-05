<template>
  <div class="dashboard-container">
    <div class="dashboard-form">
      <el-form ref="form" :model="form" label-width="80px">
        <el-form-item label="参数1">
          <el-input v-model="form.text1" size="small"></el-input>
        </el-form-item>
        <el-form-item label="参数2">
          <el-select v-model="form.text2" size="small" placeholder="请选择活动区域">
            <el-option label="区域一" :value="1"></el-option>
            <el-option label="区域二" :value="2"></el-option>
            <el-option label="区域三" :value="3"></el-option>
            <el-option label="区域四" :value="4"></el-option>
          </el-select>
        </el-form-item>
        <el-form-item label="参数3">
          <el-col :span="11">
            <el-date-picker type="date" size="small" placeholder="选择日期" v-model="form.text3" style="width: 100%;"></el-date-picker>
          </el-col>
          <el-col class="line" :span="2">-</el-col>
          <el-col :span="11">
            <el-time-picker placeholder="选择时间" size="small" v-model="form.text4" style="width: 100%;"></el-time-picker>
          </el-col>
        </el-form-item>
        <el-form-item label="参数4">
          <el-switch size="small" v-model="form.text5" active-color="#13ce66"
          inactive-color="#ff4949"></el-switch>
        </el-form-item>
        <el-form-item label="参数5">
          <el-checkbox-group size="small" v-model="form.text6">
            <el-checkbox label="属性1" name="type"></el-checkbox>
            <el-checkbox label="属性2" name="type"></el-checkbox>
            <el-checkbox label="属性3" name="type"></el-checkbox>
            <el-checkbox label="属性4" name="type"></el-checkbox>
          </el-checkbox-group>
        </el-form-item>
        <el-form-item label="参数6">
          <el-radio-group size="small" v-model="form.text7">
            <el-radio label="属性1"></el-radio>
            <el-radio label="属性2"></el-radio>
          </el-radio-group>
        </el-form-item>
        <el-form-item label="参数7">
          <el-input type="textarea" size="small" v-model="form.text8"></el-input>
        </el-form-item>
        <el-form-item>
          <el-button type="warning" size="mini" @click="onSubmit">确定</el-button>
        </el-form-item>
      </el-form>
    </div>
    <div class="dashboard-text">
      <div class="imgcontainer">
        <img v-if="img" style="height: 500px;width: 850px;object-fit: contain;" :src="img"/>
        <div v-else style="height: 500px;width: 900px;"></div>
      </div>
      <!-- <div style="display: flex;justify-content: flex-end;margin-right: 30px;">
        <el-button type="danger" size="small" @click="">预测评价</el-button>
      </div> -->
    </div>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  name: 'Dashboard',
  computed: {
    ...mapGetters([
      'name'
    ])
  },
  data() {
    return {
      form: {
        text1: '',
        text2: '',
        text3: '',
        text4: '',
        text5: '',
        text6: '',
        text7: '',
        text8: ''
      },
      img: ""
    }
  },
  methods: {
    onSubmit() {
      if(this.form.text2 == 1) {
        this.img = require("@/assets/pic1.png");
      }
      else if(this.form.text2 == 2) {
        this.img = require("@/assets/pic2.png");
      }
      else if(this.form.text2 == 3) {
        this.img = require("@/assets/pic3.png");
      }
      else if(this.form.text2 == 4) {
        this.img = require("@/assets/pic4.png");
      }
    }
  }
}
</script>

<style>
.dashboard-form .el-form-item__label {
  color: #101010;
}
.dashboard-form .el-checkbox__label {
  color: #434447;
}
.dashboard-form .el-radio__label {
  color: #434447;
}
</style>
<style lang="scss" scoped>
.dashboard {
  &-container {
    height: calc(100vh - 50px);
    min-height: 600px;
    background-image: url(../../assets/screen-bg.png);
    background-color: rgba(31, 144, 250, 0.611);
    background-size: 100%;
    display: flex;

  }
  &-form {
    flex-grow: 0;
    flex-shrink: 0;
    flex-basis: 400px;
    padding: 20px;
    overflow-y: scroll;
    // border-right: 1px solid #434447;
  }
  &-form::-webkit-scrollbar{
    display: none;
  }
  &-text {
    font-size: 30px;
    line-height: 46px;
    flex-grow: 1;
    flex-shrink: 1;
    .imgcontainer{
      margin-top: 20px;
      display: flex;
      justify-content: center;
    }
  }
}
</style>
