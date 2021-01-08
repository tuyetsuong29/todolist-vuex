<template>
  <div class="get-task">
    <form class="form" @submit.prevent="addTask">
      <input
        class="form-control"
        :value="newTask"
        @change="getTask"
        placeholder="Type you plan..."
      />
      <br />
      <button type="submit" class="button">Add Task</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "get-task",
  methods: {
    getTask(e) {
      this.$store.dispatch("getTask", e.target.value);
    },
    addTask(e) {
      e.preventDefault();
      this.$store.dispatch("addTask");
      this.$store.dispatch("clearTask");
    },
  },
  computed: {
    newTask() {
      return this.$store.getters.newTask;
    },
  },
};
</script>
<style scoped>
.form {
  display: flex;
  flex-direction: row;
  justify-content: center;
}
.form-control {
  padding: 0.5rem;
}
button {
  font: inherit;
  border: 1px solid #0076bb;
  background-color: #0076bb;
  color: white;
  cursor: pointer;
  padding: 0.5rem 1rem;
  border-radius: 10px;
}
button:hover,
button:active {
  border-color: #002350;
  background-color: #002350;
}
</style>
