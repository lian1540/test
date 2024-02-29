<template>
  <div>
    <p>第三题 使用 Element-UI的el-table 进行数据嵌套展示</p>
    <!-- 用户分组表格 -->
    <el-table :data="groupedData" style="width: 100%" border>
      <!-- 分组 ID -->
      <el-table-column prop="groupId" label="Group ID" sortable>
      </el-table-column>
      <!-- 分组名称 -->
      <el-table-column prop="groupName" label="Group Name" sortable>
      </el-table-column>
      <!-- 嵌套用户信息表格 -->
      <el-table-column label="Users">
        <template slot-scope="scope">
          <el-table :data="scope.row.users" style="width: 100%" border>
            <!-- 用户名 -->
            <el-table-column prop="name" label="Name" sortable>
            </el-table-column>
            <!-- 邮箱 -->
            <el-table-column prop="email" label="Email" sortable>
            </el-table-column>
            <!-- 角色 -->
            <el-table-column prop="role" label="Role" sortable>
            </el-table-column>
            <!-- 创建时间，使用formatter进行格式化 -->
            <el-table-column prop="createdAt" label="Created At" sortable :formatter="formatDate">
            </el-table-column>
          </el-table>
        </template>
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
import moment from 'moment'; // 引入moment库来格式化日期

export default {
  data() {
    return {
      groupedData: [] // 用于存储从API获取的分组数据
    };
  },
  created() {
    this.fetchGroupData();
  },
  methods: {
    fetchGroupData() {
      const data =
      {
        status: "success",
        data: [
          {
            groupId: 1,
            groupName: "Admin Group",
            users: [
              {
                id: 1,
                name: "John Doe",
                email: "john.doe@example.com",
                role: "admin",
                createdAt: "2023-01-01T00:00:00Z"
              },
              // 更多用户...
            ]
          },
          {
            groupId: 2,
            groupName: "Editor Group",
            users: [
              // ...
            ]
          },
          // 更多用户组...
        ]
      }

this.groupedData=data.data



    },
    formatDate(dateString) {
      // 使用moment格式化日期
      return moment(dateString).format('YYYY-MM-DD HH:mm:ss');
    }
  }
};
</script>