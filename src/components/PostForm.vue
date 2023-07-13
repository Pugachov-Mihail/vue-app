<template>
  <div>
    <form @submit.prevent>
      <h4>Создание</h4>
      <input
          v-model="post.title"
          class="input"
          type="text"
          placeholder="Название">

      <input
          v-model="post.body"
          class="input"
          type="text"
          placeholder="Описание">
      <button class="btn" @click="createPost">Сохранить</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "PostForm",
  data(){
    return {
      post: {
        title: '',
        body: ''
      }
    }
  },
  methods: {
    createPost(){
      this.post.id = Date.now();
      this.$emit('create', this.post);
      this.post = {
        title: "",
        body: ""
      }
    }
  }
}
</script>

<style scoped>
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
  .btn {
    width: 20%;
    align-self: flex-end;
    margin-top: 15px;
    background: none;
    color: teal;
    border: 1px solid teal;
  }
</style>