<template>
  <header>
    <h1>{{ title }}</h1>

    <ul class="nav">
      <li v-for="{ path, name } in navList" :key="path">
        <nuxt-link :to="path">{{ name }}</nuxt-link>
      </li>
    </ul>
  </header>
</template>

<script>
export default {
  props: {
    title: { type: String },
    navList: { type: Array, default: () => [] },
  },
};
</script>

<style scoped>
header {
  display: flex;
  align-items: stretch;
  justify-content: space-between;

  padding: 0 16px;

  background: #181818;
  color: #fff;
}

h1 {
  margin: 0;
  padding: 8px;
}

.nav {
  display: flex;
  align-items: stretch;
}

.nav li + li {
  margin-left: 8px;
}

.nav li:hover {
  background: #fff;
  color: #181818;
}

.nav li:hover a {
  color: #181818;
}

.nav li a {
  display: flex;
  align-items: center;

  color: #fff;
  text-decoration: none;
  height: 100%;
  padding: 0 16px;
}
</style>
