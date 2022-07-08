<template>
  <div>
    <h3>List of Users</h3>
    <post-item v-for="post in posts" :key="post.id" :post="post" />
  </div>
</template>

<script>
import PostItem from "@/components/PostItem";
export default {
  name: "PostsList",
  components: { PostItem },
  props: {
    posts: {
      type: Array,
      required: true,
    },
    deletePost: {
      type: Function,
      required: true,
    },
  },
};
</script>

<style scoped></style>
