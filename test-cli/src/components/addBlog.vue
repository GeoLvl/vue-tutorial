<template>
  <div id="add-blog">
    <h2>Add a new blog post</h2>
    <form action="">
      <label for="">Blog title:</label>
      <input type="text" v-model.lazy="blog.title" required />
      <label for="">Blog content:</label>
      <textarea v-model.lazy="blog.content" />
    </form>
    <div id="preview">
      <h3>preview blog</h3>
      <p>Blog title: {{ blog.title }}</p>
      <p>Blog content: {{ blog.content }}</p>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      blog: {
        title: "",
        content: ""
      }
    };
  },

  methods: {}
};
</script>

<style scoped>
#add-blog * {
  box-sizing: border-box;
}
#add-blog {
  margin: 20px auto;
  max-width: 500px;
}
label {
  display: block;
  margin: 20px 0 10px;
}
input[type="text"],
textarea {
  display: block;
  width: 100%;
  padding: 8px;
}
#preview {
  padding: 10px 10px;
  border: 1px dotted #ccc;
}
h3 {
  margin-top: 10px;
}
</style>
