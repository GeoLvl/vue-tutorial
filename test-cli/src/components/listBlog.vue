<template>
  <div v-theme:column="'narrow'" id="show-blog">
    <h1>List blog titles</h1>
    <input type="text" v-model="search" placeholder="search blogs" />
    <div v-for="blog in filteredBlogs" class="single-blog">
      <h2 v-rainbow>{{ blog.title | uppercase }}</h2>
    </div>
  </div>
</template>

<script>
import searchMixin from "../mixins/searchMixin";

export default {
  components: {},
  data() {
    return {
      blogs: [],
      search: ""
    };
  },

  methods: {
    post: function() {
      this.$http
        .post("https://jsonplaceholder.typicode.com/posts", {
          title: this.blog.title,
          body: this.blog.content,
          userId: 1
        })
        .then(function(data) {
          console.log(data);
          this.submitted = true;
        });
    }
  },
  created() {
    this.$http
      .get("https://jsonplaceholder.typicode.com/posts")
      .then(function(data) {
        console.log(data);
        this.blogs = data.body.slice(0, 10);
      });
  },
  computed: {
    // before put it in mixins folder
    // filteredBlogs: function() {
    //   return this.blogs.filter(blog => {
    //     return blog.title.match(this.search);
    //   });
    // }
  },

  //Filters locally (2 différentes écritures)
  filters: {
    uppercase(value) {
      return value.toUpperCase();
    },
    snippet: function(value) {
      return value.slice(0, 100) + "...";
    }
  },
  mixins: [searchMixin]
};
</script>

<style scoped>
#show-blog {
  max-width: 800px;
  margin: 0 auto;
}
.single-blog {
  padding: 20px;
  margin: 20px 0;
  box-sizing: border-box;
  background: #eee;
}
</style>
