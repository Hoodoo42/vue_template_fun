<template>
  <div>
    <!-- adding data binding to seamlessly allow the js and html to work together with less steps than vanilla js -->
    <!-- this v-if is conditional rendering and is looking to check if the value of show_post is true or false -->
    <!-- the button has a form of event listening on it that when clicked will react to the true/false value and either display or remove the blog  -->
    <button @click="toggleBlog">on/off</button>
<!-- putting the rendering conditional into a container that will hold all the posts not just one -->
    <section v-if="show_post === true">
      <!-- the article has a loop that will loop through the blogs to display each one on the page -->
      <article v-for="(blog, index) in blogs" :key="index">
        <h1>{{ blog[`blog_title`] }}</h1>
        <p>{{ blog[`blog_content`] }}</p>
        <img :src="blog[`blog_image_url`]" alt="" />
      </article>
    </section>
  </div>
</template>

<script>
export default {
  //   this is the function that the button is using
  methods: {
    // shortcut
    // toggleBlog() this.show_post = !this.show_post

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
    //   show_posts is setting the defualt value to true which will have the blogs displayed until the button is clicked
      show_post: true,
      blogs: [
        {
          blog_title: `First blog`,
          blog_content: `This is my first blog`,
          blog_image_url: `https://images.unsplash.com/photo-1485988412941-77a35537dae4?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1796&q=80`,
        },

        {
          blog_title: `Second blog`,
          blog_content: `This is my second blog`,
          blog_image_url: `https://images.unsplash.com/photo-1453928582365-b6ad33cbcf64?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1773&q=80`,
        },
      ],
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