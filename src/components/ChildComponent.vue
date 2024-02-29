<template>
  <div>
    <card-component
      v-for="user in users"
      :key="user.id"
      :user="user"
      @requestUpdate="$emit('updateUser', user)"
    />
  </div>
</template>

<script>
import CardComponent from './CardComponent.vue';

export default {

  components: {
    CardComponent
  },
  props: {
    users: {
      type: Array,
      required: true
    }
  },
  mounted() {
console.log("子组件:",this.users)
    
  }
};
</script>