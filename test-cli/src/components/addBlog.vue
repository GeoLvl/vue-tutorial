<template>
  <div id="add-blog">
    <h2>Add a new blog post</h2>
    <form action="">
      <label for="">Blog title:</label>
      <input type="text" v-model.lazy="blog.title" required />
      <label for="">Blog content:</label>
      <textarea v-model.lazy="blog.content" />
      <div id="checkboxes">
        <label for="">Ninjas</label>
        <input type="checkbox" value="ninjas" v-model="blog.categories" />
        <label for="">Wizards</label>
        <input type="checkbox" value="wizards" v-model="blog.categories" />
        <label for="">Mario</label>
        <input type="checkbox" value="mario" v-model="blog.categories" />
        <label for="">Cheese</label>
        <input type="checkbox" value="cheese" v-model="blog.categories" />
      </div>
    </form>
    <div id="preview">
      <h3>preview blog</h3>
      <p>Blog title: {{ blog.title }}</p>
      <p>Blog content: {{ blog.content }}</p>
      <p>Blog categories:</p>
      <ul>
        <li v-for="(category, index) of blog.categories">{{ category }}</li>
      </ul>
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
        content: "",
        categories: []
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
#checkboxes input {
  display: inline-block;
  margin-right: 10px;
}
#checkboxes label {
  display: inline-block;
}
</style>
