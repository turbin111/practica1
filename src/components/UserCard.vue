<template>
  <div class="user-card">
    <h3>{{ user.firstName }} {{ user.lastName }}</h3>
    <p>Email: {{ user.email }}</p>
  </div>
</template>

<script>
export default {
  props: {
    user: Object,
  },
};
</script>
