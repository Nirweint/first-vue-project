<template>
  <div class="post" v-for="post in posts" :key="post.id">
    <div><strong>Name:</strong> {{ post.title }}</div>
    <div><strong>Description:</strong>{{ post.description }}</div>
  </div>
</template>

<script>
export default {
  name: "PostsList",
  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
.post {
  padding: 15px;
  margin-top: 15px;
  border: 2px solid teal;
}
</style>
