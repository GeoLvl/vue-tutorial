<template>
  <div>
    <!-- <add-blog></add-blog>
    <show-blog></show-blog>
    <list-blog></list-blog> -->
    <app-header></app-header>
    <router-view></router-view>
  </div>
</template>

<script>
import addBlog from "./components/addBlog";
import showBlog from "./components/showBlog";
import listBlog from "./components/listBlog";
import header from "./components/header";

export default {
  components: {
    "add-blog": addBlog,
    "show-blog": showBlog,
    "list-blog": listBlog,
    "app-header": header
  },
  data() {
    return {};
  },

  methods: {}
};
</script>

<style scoped>
body {
  margin: 0;
  font-family: "Courier New", Courier, monospace;
}
</style>
