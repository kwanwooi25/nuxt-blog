<template>
  <div>
    <h2>{{ post.title }}</h2>
    <p>{{ post.body }}</p>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  layout: 'MainLayout',

  async asyncData({ params: { id } }) {
    const res = await axios.get(`https://jsonplaceholder.typicode.com/posts/${id}`);
    return { post: res.data };
  },
};
</script>
