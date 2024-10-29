<template>
  <div>
    <h2>Login</h2>
    <form @submit.prevent="login">
      <input v-model="username" type="text" placeholder="Username" required />
      <input v-model="password" type="password" placeholder="Password" required />
      <button type="submit">Login</button>
      <p v-if="errorMessage" style="color: red">{{ errorMessage }}</p>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: '',
      password: '',
      errorMessage: '',
    };
  },
  methods: {
    async login() {
      this.errorMessage = ''; // Сброс ошибки перед попыткой логина

      try {
        const response = await fetch('https://dummyjson.com/auth/login', {
          method: 'POST',
          headers: { 'Content-Type': 'application/json' },
          body: JSON.stringify({ username: this.username, password: this.password }),
        });

        const data = await response.json();

        if (data.accessToken) {
          // Сохраняем accessToken вместо token
          localStorage.setItem('token', data.accessToken);
          this.$router.push('/profile');
        } else {
          this.errorMessage = data.message || 'Login failed';
        }
      } catch (error) {
        console.error('Login error:', error);
        this.errorMessage = 'Authorization failed';
      }
    },
  },
};
</script>
