<template>
  <div id="app">
    <HelloWorld :msg="sssss" /> 
    <el-divider></el-divider>

    <MyComponent />
    <el-divider></el-divider>

    <ProductList />
    <el-divider></el-divider>

    <QuestionThree />
    <el-divider></el-divider>

    <ParentComponent />
    <el-divider></el-divider>
    <UserManagementComponent />
  </div>
</template>

<script>
// 
 import HelloWorld from './components/HelloWorld.vue'
import MyComponent from './components/QuestionOne.vue'
import ProductList from './components/ProductList.vue'
import QuestionThree from './components/QuestionThree.vue'
import ParentComponent from './components/ParentComponent.vue'
import UserManagementComponent from './components/UserManagementComponent.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    MyComponent,
    ProductList,QuestionThree,ParentComponent,UserManagementComponent
  },
  created()
  {
    this.sssss="sadasdsa "
   }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
