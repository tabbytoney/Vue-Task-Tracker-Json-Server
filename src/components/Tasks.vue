<template>
  <!-- take in a prop of the tasks (as an array) then loop through them
     then output a single task component for each one -->
  <div :key="task.id" v-for="task in tasks">
    <!-- For each individual task: -->
    <!-- <h3>{{ task.test }}</h3> -->
    <!-- The below 'task' renders the individual object -->
    <Task
      @toggle-reminder="$emit('toggle-reminder', task.id)"
      @delete-task="$emit('delete-task', task.id)"
      :task="task"
    />
  </div>
</template>

<script>
import Task from "./Task.vue";
// take in tasks array as a prop
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Tasks",
  props: {
    tasks: Array,
  },
  components: {
    Task,
  },
  emits: ["delete-task", "toggle-reminder"],
};
</script>
