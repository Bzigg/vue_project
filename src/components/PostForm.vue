<template>
  <form @submit.prevent>
    <h4>Новый пост</h4>
    <input
      v-model="post.title"
      type="text"
      class="input"
      placeholder="Заполните заголовок"
    />
    <input
      v-model="post.discription"
      type="text"
      class="input"
      placeholder="Заполните описание"
    />
    <button class="btn" @click="createPost">Добавить</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: "",
        discription: "",
      },
    };
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit("create", this.post);
      this.post = {
        title: "",
        discription: "",
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
.input {
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}
.btn {
  margin-top: 15px;
  padding: 10px 15px;
  align-self: flex-end;
  background: none;
  color: teal;
  border: 1px solid teal;
}
</style>