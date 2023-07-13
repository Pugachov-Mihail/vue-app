<template>
  <div>
    <PostForm @create="createPost"/>
    <PostList :posts="posts"/>
  </div>
</template>

<script>
import PostForm from "@/components/PostForm";
import PostList from "@/components/PostList";

export default {
  name: "App",
  components: {PostForm, PostList},
  data(){
    return {
     posts: [
       {id: 1, title: "Какое то сообщение", body: "Какой то текст"},
       {id: 2, title: "Какое то сообщение 2", body: "Какой то текст 2"},
     ],
    }
  },
  methods: {
    createPost(post){
        this.posts.push(post)
    },
  }
}
</script>

<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
</style>