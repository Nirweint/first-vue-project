<template>
  <form @submit.prevent>
    <h4>Create post</h4>
    <input v-model="post.title" class="input" type="text" placeholder="title" />
    <input
      v-model="post.description"
      class="input"
      type="text"
      placeholder="description"
    />
    <button class="btn" @click="createPost">Create post</button>
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
.btn {
  margin-top: 15px;
  align-self: flex-end;

  padding: 10px 15px;
  background: none;
  color: teal;
  border: 1px solid teal;
}

.input {
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}

form {
  display: flex;
  flex-direction: column;
}
</style>
