<template>
  <div>
    <el-card class="box-card">
  <div slot="header" class="clearfix">
    <span>id</span>:{{user.id}}
    <span>姓名</span>:{{user.name}}
   

    <el-button style="float: right; padding: 3px 0" type="text">操作按钮</el-button>
  </div>

  <el-form ref="form" :model="user" label-width="80px">
  <el-form-item label="邮箱">
    <el-input :value="user.name"></el-input>
  </el-form-item>
  <el-form-item label="角色">
    <el-input :value="user.role"></el-input>
  </el-form-item>
</el-form>

</el-card>
  </div>
</template>

<script>


export default {
  components: {
    
  },
  props: {
    user: {
      type: Object,
      required: true
    }
  },
  mounted()
  {
console.log("卡片组件",this.user)

    
  }
};
</script>


<style>
  .text {
    font-size: 14px;
  }

  .item {
    margin-bottom: 18px;
  }

  .clearfix:before,
  .clearfix:after {
    display: table;
    content: "";
  }
  .clearfix:after {
    clear: both
  }

  .box-card {
    width: 480px;
  }
</style>