<template>
  <div v-if="user">
    <h2>User Profile</h2>
    <img :src="user.image" alt="User Image" />
    <p>Name: {{ user.firstName }} {{ user.lastName }}</p>
    <p>Email: {{ user.email }}</p>
    <p>Age: {{ user.age }}</p>
    <p>Phone: {{ user.phone }}</p>
    <p>Country: {{ user.address.country }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      user: null,
    };
  },
  async created() {
    const token = localStorage.getItem('token');
    if (token) {
      const response = await fetch('https://dummyjson.com/auth/me', {
        headers: { Authorization: `Bearer ${token}` },
      });
      const data = await response.json();
      if (data.id) {
        this.user = data;
      } else {
        localStorage.removeItem('token');
        this.$router.push('/login');
      }
    } else {
      this.$router.push('/login');
    }
  },
};
</script>
