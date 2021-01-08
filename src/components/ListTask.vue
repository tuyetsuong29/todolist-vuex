<template>
  <div class="list-task">
    <div class="boxList">
      <h3>
        My Tasks <span v-if="tasks.length > 0">{{ tasks.length }}</span>
      </h3>
      <div class="edit-task">
        <ul>
          <li v-for="(task, index) in tasks" v-bind:key="index">
            {{ task.body }}
            <dmiv class="btn-group">
              <button
                type="button"
                @click="edit(task)"
                href="#edit"
                role="button"
                data-toggle="modal"
              >
                <span></span> Edit
              </button>
              <button type="button" @click="complete(task)">
                <span> </span>Complete
              </button>
              <button type="button" @click="remove(task)">
                <span></span> Remove
              </button>
            </dmiv>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "list-task",
  methods: {
    edit(task) {
      this.$store.dispatch("editTask", task);
    },
    complete(task) {
      this.$store.dispatch("completeTask", task);
    },
    remove(task) {
      this.$store.dispatch("removeTask", task);
    },
  },
  computed: {
    tasks() {
      return this.$store.getters.tasks;
    },
  },
};
</script>
<style scoped>
ul {
  margin: 0;
  padding: 0;
  height: 100%;
}
li {
  margin: 0 2rem;
}
.boxList {
  margin-left: 2rem;
}
</style>
