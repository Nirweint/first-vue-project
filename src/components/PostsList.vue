<template>
  <div v-if="posts.length > 0">
    <h3>List of Users</h3>
    <post-item
      v-for="post in posts"
      :key="post.id"
      :post="post"
      @deletePost="$emit('deletePost', post.id)"
    />
  </div>
  <h2 v-else>List of the users are empty.</h2>
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
