<template>
  <div>
    <h3>Список пользователей</h3>
  </div>
  <post-item
      :post="post"
      v-for="post in posts" />
</template>

<script>
import PostItem from "@/components/PostItem";
export default {
  name: "PostList",
  components: {PostItem},
  props: {
    posts: {
      type: Array,
      required: true
    }
  }
}
</script>

<style scoped>

</style>