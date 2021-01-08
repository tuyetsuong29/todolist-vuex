<template>
  <div id="app">
    <get-task></get-task>
    <list-task></list-task>
    <completed-task></completed-task>
  </div>
</template>

<script>
import GetTask from "./components/GetTask.vue";
import ListTask from "./components/ListTask.vue";
import CompletedTask from "./components/CompletedTask.vue";

export default {
  name: "App",
  components: {
    GetTask,
    ListTask,
    CompletedTask,
  },
};
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-top: 3rem;
}
</style>
