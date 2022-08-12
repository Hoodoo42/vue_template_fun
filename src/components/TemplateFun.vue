<template>
  <div>
    <!-- adding data binding to seamlessly allow the js and html to work together with less steps than vanilla js -->
    <!-- this v-if is conditional rendering and is looking to check if the value of show_post is true or false -->
    <!-- the button has a form of event listening on it that when clicked will react to the true/false value and either display or remove the blog  -->
    <h1 v-if="show_post === true">{{ blog_title }}</h1>
    <p v-if="show_post === true">{{ blog_content }}</p>
    <img v-if="show_post === true" :src="blog_image_url" alt="" />
    <button @click="toggleBlog">on/off</button>
  </div>
</template>

<script>
export default {
  //   this is the function that the button is using
  methods: {
    toggleBlog() {
      if (this.show_post === true) {
        this.show_post = false;
      } else {
        this.show_post = true;
      }
    },
  },

  data() {
    return {
      //   this is the data being sent up to HTML to diplay on the browser
      blog_title: `First blog`,
      blog_content: `This is my first blog`,
      blog_image_url: `https://images.unsplash.com/photo-1485988412941-77a35537dae4?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1796&q=80`,
      show_post: true,
    };
  },
};
</script>

<style scoped>
img {
  width: 150px;
  height: 150px;
}
</style>