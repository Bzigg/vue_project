<template>
  <div class="app">
    <post-form @create="createPost" />
    <post-list :posts="posts" />
  </div>
</template>

<script>
import PostForm from "@/components/PostForm";
import PostList from "@/components/PostList";
export default {
  components: {
    PostForm,
    PostList,
  },
  data() {
    return {
      posts: [
        { id: 1, title: "JS", discription: "JS lorem ipsum dolor sit amolet." },
        { id: 2, title: "PHP", discription: "PHP orem ipsum dolor sit." },
        { id: 3, title: "Py3", discription: "Py3 world dolor ." },
        { id: 4, title: "C++", discription: "C++ world dolor ." },
      ],
    };
  },
  methods: {
    createPost(post) {
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
  padding: 20px;
}
</style>