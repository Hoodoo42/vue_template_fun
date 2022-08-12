<template>
  <div>
    <h1>{{ blog_title }}</h1>
    <p>{{ blog_content }}</p>
    <img :src="blog_image_url" alt="">
  </div>
</template>

<script>
export default {
  data() {
    return {
      
      blog_title: `First blog`,
      blog_content: `This is my first blog`,
      blog_image_url: `https://images.unsplash.com/photo-1485988412941-77a35537dae4?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1796&q=80`,
    };
  },
};
</script>

<style scoped>
</style>