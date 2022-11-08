<template>
  <header>
    <h1>{{ title }}</h1>
    <Button
      v-show="homePage"
      @btn-click="$emit('toggle-add-task')"
      :color="showAddTask ? 'red' : 'green'"
      :text="showAddTask ? 'Close' : 'Add Task'"
    />
  </header>
</template>

<script>
import Button from './Button';

export default {
  name: 'Header',
  props: {
    title: {
      type: String,
      default: 'Hello World',
    },
    showAddTask: Boolean,
  },
  components: { Button },
  computed: {
    homePage() {
      if (this.$route.path === '/') {
        return true;
      } else {
        return false;
      }
    },
  },
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>
