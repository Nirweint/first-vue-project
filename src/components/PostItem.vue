<template>
  <div class="post">
    <div>
      <div><strong>Name:</strong> {{ post.title }}</div>
      <div><strong>Description:</strong>{{ post.description }}</div>
    </div>
    <div class="post__buttons">
      <common-button @click="$emit('deletePost', post.id)"
        >Delete me</common-button
      >
    </div>
  </div>
</template>

<script>
export default {
  name: "PostItem",
  props: {
    post: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.post {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 15px;
  margin-top: 15px;
  border: 2px solid teal;
}
</style>
