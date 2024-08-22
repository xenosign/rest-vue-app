// App.vue
<template>
  <div class="app-container">
    <Header @change-component="changeComponent" />
    <div class="board-container">
      <Todo v-if="currentComponent === 'todo'" />
      <Weather v-if="currentComponent === 'weather'" />
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Todo from './components/Todo.vue';
import Weather from './components/Weather.vue';

export default {
  components: {
    Header,
    Todo,
    Weather,
  },
  data() {
    return {
      currentComponent: 'todo',
    };
  },
  methods: {
    changeComponent(component) {
      this.currentComponent = component;
    },
  },
};
</script>

<style scoped>
.app-container {
  display: flex;
  flex-direction: column;
}

.board-container {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  background-color: #333;
}

.board-container > * {
  flex: 1;
  margin: 10px;
  max-width: 700px;
}
</style>
