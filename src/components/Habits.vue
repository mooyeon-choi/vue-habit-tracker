<template>
  <div class="habits">
    <HabitAddForm @add="$emit('add', $event)"/>
    <ul v-for="(habit, index) in habits" :key="index">
      <Habit 
        :habit="habit" 
        @increment="$emit('increment', index)" 
        @decrement="$emit('decrement', index)"
        @delete="$emit('delete', index)"
      />
    </ul>
    <button class="habits-reset" @click="$emit('reset')">
      Reset All
    </button>
  </div>
</template>
<script>
import Habit from './Habit.vue'
import HabitAddForm from './HabitAddForm.vue'
export default {
  props: ['habits'],
  components: { Habit, HabitAddForm },
}
</script>
<style>
.habits {
  padding: 0.5em;
  padding-top: 2em;
}

.habits-reset {
  font-size: 1.5rem;
  padding: 0.2em 1em;
  background-color: green;
  color: white;
}
</style>