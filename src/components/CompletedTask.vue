<template>
  <div class="completed-task">
    <div>
      <h3>
        Completed
        <span v-if="completed.length > 0">{{ completed.length }}</span>
      </h3>

      <div>
        <ul>
          <li v-for="(task, index) in completed" v-bind:key="index">
            {{ task.body }}
            <button type="button" @click="remove(task)">
              <span></span> Remove
            </button>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "completed-task",
  methods: {
    remove(task) {
      this.$store.dispatch("removeTask", task);
    },
  },
  computed: {
    completed() {
      return this.$store.getters.completedTask;
    },
  },
};
</script>
<style scoped>
.completed-task {
  margin-left: 2rem;
}
</style>
