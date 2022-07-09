<template>
  <div class="app">
    <h1>Page with the posts</h1>
    <common-button @click="handleCreateNewPostClick"
      >Create new post</common-button
    >
    <common-modal v-model:isShowModal="isModalOpen">
      <post-form @create="onCreatePostClick" />
    </common-modal>
    <posts-list :posts="posts" @deletePost="deletePost" />
  </div>
</template>

<script>
import PostsList from "@/components/PostsList";
import PostForm from "@/components/PostForm";

export default {
  components: {
    PostForm,
    PostsList,
  },
  name: "App",
  data() {
    return {
      posts: [
        {
          id: 1,
          title: "Javascript 1",
          description: "Javascript description 1",
        },
        {
          id: 2,
          title: "Javascript 2",
          description: "Javascript description 2",
        },
        {
          id: 3,
          title: "Javascript 3",
          description: "Javascript description 3",
        },
      ],
      isModalOpen: false,
    };
  },
  methods: {
    onCreatePostClick(post) {
      this.posts.push(post);
      this.isModalOpen = false;
    },
    deletePost(id) {
      this.posts = this.posts.filter((p) => p.id !== id);
    },
    handleCreateNewPostClick() {
      this.isModalOpen = true;
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  padding: 15px;
}
</style>
