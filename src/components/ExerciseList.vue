


<template>

<div>

<p>Completed Exercises: {{exercises.filter(exercise => {return exercise.done === true}).length}}</p>
<p>Incompleted Exercises: {{exercises.filter(exercise => {return exercise.done === false}).length}}</p>
<display-exercise v-on:complete-exercise="completeExercise" v-for="exercise in exercises" v-bind:exercise="exercise" :key="exercise.id"></display-exercise>
</div>
</template>



<script type="text/javascript">

import DisplayExercise from './DisplayExercise'

export default {

props: ['exercises'], 
components: {
    DisplayExercise,
},
methods: {
completeExercise(exercise) {
    const exerciseIndex = this.exercises.indexOf(exercise); 
    this.exercises[exerciseIndex].done = true; 
    alert('Success!', 'Exercise complete!', 'success')
},
}, 
}; 

</script>


<style>


</style>