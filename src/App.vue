<template>
  <div id="app">
    <Navbar />
    <ul class="habits" v-for="habit in habits" :key="habit.id">
      <Habit :habit="habit" @increment="increment(habit)"/>
    </ul>
  </div>
</template>

<script>
import Habit from './components/Habit.vue'
import Navbar from './components/Navbar.vue'

export default {
  name: 'App',
  components: {
    Navbar,
    Habit,
  },
  data() {
    return {
      habits: [
        { id: 1, name: 'Reading', count: 0},
        { id: 2, name: 'Running', count: 0},
        { id: 3, name: 'Coding', count: 0}
      ]
    }
  },
  methods: {
    increment(habit) {
      console.log(habit)
    }
  }
}
</script>

<style>
body {
  margin: 0;
}

#app {
  box-sizing: border-box;
}

.habits {
  padding: 0.5em;
  padding-top: 2em;
}

button {
  outline: none;
  border: 0;
  cursor: pointer;
}
</style>
