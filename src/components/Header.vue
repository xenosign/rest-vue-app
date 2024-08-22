<template>
  <header>
    <nav>
      <button
        @click="$emit('change-component', 'todo')"
        :class="{ active: currentComponent === 'todo' }"
      >
        Todo
      </button>
      <button
        @click="$emit('change-component', 'weather')"
        :class="{ active: currentComponent === 'weather' }"
      >
        Weather
      </button>
    </nav>
  </header>
</template>

<script>
export default {
  props: ['currentComponent'],
};
</script>

<style scoped>
header {
  background-color: #4a4a4a;
  padding: 1rem;
}

nav {
  display: flex;
  justify-content: center;
}

button {
  background: none;
  border: none;
  color: white;
  cursor: pointer;
  font-size: 1.2rem;
  margin: 0 1rem;
  padding: 0.5rem 1rem;
}

button.active {
  font-weight: bold;
  border-bottom: 2px solid white;
}
</style>
