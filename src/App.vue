<template>
  <div id="app">
    <h1>Belajar submit form dengan Vue Js</h1>

    <PostForm />
  </div>
</template>

<script>
import PostForm from "./components/PostForm";

export default {
  name: "App",
  components: {
    PostForm,
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
