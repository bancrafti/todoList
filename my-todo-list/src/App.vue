<template>
  <div id="app" class="fullscreen">
    <TodoList />
  </div>
</template>

<script lang="ts">
import TodoList from './components/TodoList.vue';

export default {
  components: {
    TodoList
  }
};
</script>

<style scoped>
#app {
  background-color: #f0f8ff; /* Light blue background */
  color: #333; /* Dark text color */
  padding: 20px;
  border-radius: 8px;
}

.fullscreen {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100vw;
  height: 100vh;
  margin: 0;
  padding: 0;
  overflow: hidden;
}
</style>