<template>
  <div>
    第四题:父子组件传值
    
    <child-component :users="users" @updateUser="fetchUsers" />
  </div>
</template>

<script>
import ChildComponent from './ChildComponent.vue';

export default {
  components: {
    ChildComponent
  },
  data() {
    return {
      users: []
    };
  },
  created() {
    this.fetchUsers();
  },
  methods: {
    fetchUsers() {  
       this.users=[
      {
        id: 1,
         name: "John Doe",
         email: "john.doe@example.com",
         role: "admin",
         createdAt: "2023-01-01T00:00:00Z"
       },
       {
        id: 2,
         name: "John Doe",
         email: "john.doe@example.com",
         role: "admin",
         createdAt: "2023-01-01T00:00:00Z"
       },
       {
        id: 3,
         name: "John Doe",
         email: "john.doe@example.com",
         role: "admin",
         createdAt: "2023-01-01T00:00:00Z"
       },
     ]

    }
  }
};
</script>