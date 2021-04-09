<template>
 <div id="app">
 <exercise-list v-bind:exercises="exercises"></exercise-list>
 <add-exercise v-on:add-exercise="addExercise"></add-exercise>
 </div>
</template>

<script>
import ExerciseList from './components/ExerciseList.vue'
import AddExercise from './components/AddExercise.vue'


export default {
name: 'app',
 components: {
   ExerciseList,
   AddExercise,
 },
  
data() {
  return {
    exercises: [
      {
      title: 'Aerobics', 
      time: '', 
      distance: '', 
      sets: '', 
      reps: '', 
      weight: '', 
      done: false,
    }, 
      {
      title: 'Yoga', 
      time: '', 
      distance: '', 
      sets: '', 
      reps: '', 
      weight: '', 
      done: false,
    }, 
      {
      title: 'Cardio', 
      time: '', 
      distance: '', 
      sets: '', 
      reps: '', 
      weight: '', 
      done: false,
    }], 
  }
}, 
methods: {
  addExercise(newExercise) {
    this.exercises.push(newExercise)
  }
}

 
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
