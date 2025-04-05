<template>
  <div class="dashboard-container">
    <div class="dashboard-form">
      <el-table
        :data="tableData"
        stripe
        style="width: 100%">
        <el-table-column
          type="index"
          label="序号"
          width="50">
        </el-table-column>
        <el-table-column
          prop="name"
          label="元素名称"
          width="180">
        </el-table-column>
        <el-table-column
          prop="type1"
          label="W+">
        </el-table-column>
        <el-table-column
          prop="type2"
          label="W-">
        </el-table-column>
        <el-table-column
          prop="relatedNum"
          label="C(相关系数)">
        </el-table-column>
        <el-table-column
          prop="element"
          label="要素所占格子">
        </el-table-column>
      </el-table>
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
      tableData: [
        {
          name: '钻孔Ag(去边缘)',
          type1: 0.856972,
          type2: -0.04685,
          relatedNum: 0.9089,
          element: 99755
        },
        {
          name: '钻孔Ag(去边缘)',
          type1: 0.856972,
          type2: -0.04685,
          relatedNum: 0.9089,
          element: 99755
        },
        {
          name: '钻孔Ag(去边缘)',
          type1: 0.856972,
          type2: -0.04685,
          relatedNum: 0.9089,
          element: 99755
        },
        {
          name: '钻孔Ag(去边缘)',
          type1: 0.856972,
          type2: -0.04685,
          relatedNum: 0.9089,
          element: 99755
        }
      ]
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
  }
  &-form {
    padding: 20px;
  }
}
</style>
