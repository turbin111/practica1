<template>
  <div id="app">
    <header>
      <nav>
        <router-link to="/home">Home</router-link>
        <router-link to="/users">Users</router-link>
        <router-link to="/profile">Profile</router-link>
      </nav>
    </header>
    <main>
      <router-view></router-view>
    </main>
  </div>
</template>

<script>
export default {
  name: 'App',
};
</script>

<style>
/* Добавьте стили для навигации или оформления страниц */
nav {
  display: flex;
  gap: 15px;
  position: absolute; /* Устанавливаем позицию навигации абсолютной */
  top: 0px; /* От верхней границы 300 пикселей */
  right: 300px; /* От правой границы 300 пикселей */
}

#app {
  text-align: center;
  position: relative; /* Устанавливаем позицию для корректного размещения nav */
}
</style>
