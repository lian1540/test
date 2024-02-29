<template>
  <el-table :data="sortedUsers" style="width: 100%">
    <el-table-column prop="username" label="用户名"></el-table-column>
    <el-table-column prop="email" label="邮箱"></el-table-column>
    <el-table-column prop="formattedRegistrationDate" label="注册日期"></el-table-column>
    <el-table-column label="操作">
      <template slot-scope="scope">
        <el-button size="mini" @click="editUser(scope.row)">编辑</el-button>
        <el-button
          size="mini"
          type="danger"
          @click="toggleStatus(scope.row)"
        >{{ scope.row.status.description === 'Active' ? '禁用' : '启用' }}</el-button>
        <el-button size="mini" type="danger" @click="confirmDelete(scope.row)">删除</el-button>
      </template>
    </el-table-column>
  </el-table>
</template>

<script>

import { MessageBox, Message } from 'element-ui';

export default {
  data() {
    return {
      users: [],
    };
  },
  computed: {
    // 使用计算属性对用户按注册日期降序排列
    sortedUsers() {
      return this.users.sort((a, b) => {
        return new Date(b.registrationDate) - new Date(a.registrationDate);
      });
    },
  },
  created() {
    this.fetchUsers();
  },
  methods: {
    fetchUsers() {
      this.data = {
        
        status: "success",
          data: [
            {
              _id: "61f7c9e68d2fa1b8d4a2a9f0",
              username: "john.doe",
              email: "john.doe@example.com",
              registrationDate: "2022-01-01T00:00:00Z",
              status: { code: 1, description: "Active" },
            },
            // 更多用户...
          ]
      
    }


    },
    formatDate(date) {
      // 格式化日期的实现，此处可以使用库如moment.js或date-fns
      return new Date(date).toLocaleDateString();
    },
    editUser(user) {
      // 编辑用户的逻辑
      console.log('Editing user', user);
    },
    toggleStatus(user) {
      // 切换用户状态的逻辑
      const newStatus = user.status.code === 1 ? 0 : 1;
      axios.put(`/api/users/${user.id}/status`, { status: newStatus })
        .then(() => {
          user.status.code = newStatus;
          user.status.description = newStatus === 1 ? 'Active' : 'Inactive';
          Message.success(`用户状态已${newStatus === 1 ? '启用' : '禁用'}`);
        })
        .catch(error => {
          console.error('Error updating user status:', error);
          Message.error('状态更新失败');
        });
    },
    confirmDelete(user) {
      MessageBox.confirm('确认删除该用户吗?', '警告', {
        confirmButtonText: '确认',
        cancelButtonText: '取消',
        type: 'warning'
      }).then(() => {
        this.deleteUser(user);
      }).catch(() => {
        Message.info('已取消删除');
      });
    },
    deleteUser(user) {
      // 删除用户的逻辑
      axios.delete(`/api/users/${user.id}`)
        .then(() => {
          this.users = this.users.filter(u => u.id !== user.id);
          Message.success('用户删除成功');
        })
        .catch(error => {
          console.error('Error deleting user:', error);
          Message.error('用户删除失败');
        });
    },
  }
};
</script>

<style>
/* 你的样式代码 */
</style>