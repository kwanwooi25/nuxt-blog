<template>
  <div>
    <Header :title="title" :nav-list="navList" />
    <div class="contents">
      <nuxt />
    </div>
  </div>
</template>

<script>
import Header from '../components/Header';

export default {
  components: {
    Header,
  },

  data() {
    return {
      title: 'Nuxt-Blog',
      navList: [
        {
          path: '/',
          name: 'Home',
        },
        {
          path: '/posts',
          name: 'Posts',
        },
        {
          path: '/about',
          name: 'About',
        },
      ],
    };
  },
};
</script>

<style>
*,
*::before,
*::after {
  box-sizing: border-box;
}

html,
body {
  margin: 0;
  padding: 0;
}

ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

.contents {
  padding: 16px;
}
</style>
