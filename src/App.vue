<template>
  <header>
    <nav>
      <ul>
        <li class="nav-item">
          <img class="logo" src="./assets/build-a-bot-logo.png">
          Build-a-bot
        </li>
      </ul>
    </nav>
  </header>
  <main>
<!--    <RobotBuilder/>-->
    <Search/>
  </main>
</template>

<script>
// import RobotBuilder from './build/RobotBuilder.vue';
import Search from './search/Search.vue';

export default {
  name: 'App',
  components: {
    Search,
    // RobotBuilder,
  },
};
</script>

<style>
  body {
    background-image: linear-gradient(to bottom, #555, #999);
    background-attachment: fixed;
  }
</style>
<style scoped>
  main {
    margin: 0 auto;
    padding: 30px;
    background-color: #ffffff;
    width: 1024px;
    min-height: 300px;
  }
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
  }
  header {
    background-color: #999;
    width: 1084px;
    margin: 0 auto;
  }
  ul {
    padding: 3px;
    display: flex;
  }
  .nav-item {
    display: inline-block;
    padding: 5px 10px;
    font-size: 22px;
    border-right: 1px solid #bbb;
  }
  .logo {
    vertical-align: middle;
    height: 30px;
  }

</style>
