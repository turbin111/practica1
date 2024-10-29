<template>
  <div>
    <h2>Users</h2>
    <UserCard v-for="user in users" :key="user.id" :user="user" />
  </div>
</template>

<script>
import UserCard from '../components/UserCard.vue';

export default {
  components: { UserCard },
  data() {
    return {
      users: [],
    };
  },
  async created() {
    const response = await fetch('https://dummyjson.com/users');
    const data = await response.json();
    this.users = data.users;
  },
};
</script>
