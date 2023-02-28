<template>
  <header>
    <h1>{{ title }}</h1>
  </header>
  <ButtonComp
    @btn-click="$emit('toggle-add-task')"
    :text="showAddTask ? 'Close' : 'Add Task'"
    :color="showAddTask ? 'red' : 'green'"
  />
  <!-- <ButtonComp text="Update Task" color="blue" />
  <ButtonComp text="Delete Task" color="red" /> -->
</template>

<script>
import ButtonComp from "./ButtonComp";
export default {
  name: "TrackerHeader",
  //  You can define props as an array or an object
  // props: ['title']

  // To add a default value:
  // props: {
  //     title: {
  //         type: String,
  //         default: 'Hello World',
  //     }
  // }

  props: {
    title: String,
    showAddTask: Boolean,
  },
  components: {
    ButtonComp,
  },
};
</script>

// Scoped = these styles are only for this component
<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>
