<template>
  <form @submit.prevent>
    <h4>Create post</h4>
    <common-input v-model="post.title" type="text" placeholder="title" />
    <common-input
      v-model="post.description"
      type="text"
      placeholder="description"
    />
    <common-button class="form__btn" @click="createPost"
      >Create post</common-button
    >
  </form>
</template>

<script>
export default {
  name: "PostForm",
  data() {
    return {
      post: {
        title: "",
        description: "",
      },
    };
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit("create", this.post);
      this.post = {
        description: "",
        title: "",
      };
    },
  },
};
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
}

.form__btn {
  margin-top: 15px;
  align-self: flex-end;
}
</style>
