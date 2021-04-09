<template>

 <div id="app">
  <div class="header1">Vue Exercise App</div>
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
  
}

.header1 {
  background-color: navy;
  font-size: 24px; 
  line: 100; 
  padding: 20px; 
  color: white; 
}
</style>
