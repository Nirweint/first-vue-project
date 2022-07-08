<template>
  <div class="app">
    <post-form @create="onCreatePostClick" />
    <posts-list :posts="posts" />
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
    };
  },
  methods: {
    onCreatePostClick(post) {
      this.posts.push(post);
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
