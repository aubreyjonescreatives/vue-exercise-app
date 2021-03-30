<template>
  <div id="app">
   <h1>Exercise List</h1>
   <exercise-list-form />
    <exercise-list :items='exerciseItems'/>
    
  </div>
</template>

<script>
import ExerciseList from './components/ExerciseList.vue'
import AddExercise from './components/AddExercise.vue'


export default {
  name: 'App',
  components: {
    ExerciseList
  }, 
  data() {
    return {
      exerciseItems: [
        {
          id: 1, 
          name: 'Aerobics', 
          amount: 1,
        }, 
         {
          id: 2, 
          name: 'Yoga', 
          amount: 1,
        }, 
           {
          id: 3, 
          name: 'Dance', 
          amount: 1,
        }, 

      ]

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
