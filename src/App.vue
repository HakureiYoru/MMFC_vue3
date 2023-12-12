<template>
  <v-app id="inspire">
    <v-app-bar flat :elevation="4">
      <v-container class="mx-auto d-flex align-center justify-center">
        <v-avatar class="me-4" size="32">
          <img src="/ava.jpg" alt="头像" style="width: 100%; height: 100%" />
          <!-- 替换为您的图片路径 -->
        </v-avatar>

        <!-- 使用 v-btn 和 router-link 结合来创建导航链接 -->
        <v-btn text prepend-icon="$vuetify" rounded="xl">
          <router-link to="/">Welcome</router-link>
        </v-btn>
        <v-btn text prepend-icon="$vuetify" rounded="xl">
          <router-link to="/home">Home</router-link>
        </v-btn>
        <v-btn text prepend-icon="$vuetify" rounded="xl">
          <router-link to="/about">About</router-link>
        </v-btn>

        <v-spacer></v-spacer>
      </v-container>
    </v-app-bar>

    <v-main>
      <!-- 这里是页面的主要内容 -->
      <router-view />
    </v-main>

    <v-footer class="bg-indigo-lighten-1 text-center d-flex flex-column">
      <div>
        <a href="https://twitter.com/hakureiyoru" target="_blank">
          <v-btn icon class="mx-4">
            <v-icon>mdi-twitter</v-icon>
          </v-btn>
        </a>
      </div>

      <div class="pt-0">E-mail：768754163@qq.com</div>

      <v-divider></v-divider>

      <div>{{ new Date().getFullYear() }} — <strong>MMFC</strong></div>
    </v-footer>
  </v-app>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>

<script>
export default {
  name: "App",
  // 不再需要 data 部分用于图标
};
</script>
