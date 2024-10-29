<template>
  <div class="home-container">
    <h1>Home Page</h1>
    <div class="content">
      <div class="text-block">
        <p>
          Amet minim mollit non deserunt ullamco est sit aliqua dolor do amet sint. 
          Velit officia consequat duis enim velit mollit. Exercitation veniam consequat 
          sunt nostrud amet.
        </p>
        <router-link to="/login">
          <button class="login-button">Login</button>
        </router-link>
      </div>
      <div class="image-block">
        <img :src="require('@/img/img.png')" alt="home image" />

      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeView',
};
</script>

<style scoped>
.home-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 200px; /* Отступ сверху */
}

.content {
  display: flex;
  justify-content: center;
  align-items: flex-start; /* Выравнивание по верхнему краю */
  margin-top: 20px; /* Отступ сверху для контента */
  width: 100%;
  max-width: 1200px; /* Максимальная ширина для удобства */
}

.text-block {
  flex: 1; /* Занимает доступное пространство */
  padding-right: 20px; /* Отступ справа для текста */
}

.image-block {
  flex: 1; /* Занимает доступное пространство */
}

.image-block img {
  width: 301px; /* Ширина изображения */
  height: 290px; /* Высота изображения */
}
.login-button {
  margin-top: 10px; /* Отступ сверху для кнопки */
}
</style>
