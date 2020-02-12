<template>
  <div>
    <h2>Posts</h2>

    <ul>
      <li v-for="{ id, title, body } in posts" :key="id" class="post" @click="handleClickPost(id)">
        <h3>{{ title }}</h3>
        <p>{{ body }}</p>
      </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  layout: 'MainLayout',

  head() {
    return {
      title: 'Posts | Nuxt Blog',
    };
  },

  async asyncData() {
    const res = await axios.get('https://jsonplaceholder.typicode.com/posts');
    return { posts: res.data || [] };
  },

  methods: {
    handleClickPost(postId) {
      this.$router.push(`/posts/${postId}`);
    },
  },
};
</script>

<style scoped>
.post {
  border: 1px solid #181818;
  border-radius: 8px;
  cursor: pointer;
  padding: 16px;
}

.post:hover {
  background: #181818;
  color: #fff;
}

.post + .post {
  margin-top: 16px;
}

.post h3 {
  margin: 0;
}

.post p {
  margin: 8px 0 0;
}
</style>
