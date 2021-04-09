<template>
<div>

<div class="e-container">
<div v-show="!isEditing">

<div class="eInfo">
{{ exercise.date }}
</div>
<div class="eInfo">
{{ exercise.title }}
</div>
<div class="eInfo">
{{ exercise.time }}
</div>

<div class="eInfo">
{{ exercise.distance }}
</div>

<div class="eInfo">
{{ exercise.sets }}
</div>

<div class="eInfo">
{{ exercise.reps }}
</div>

<div class="eInfo">
{{ exercise.weight }}
</div>

<div class="eEdit">
<div v-on:click="showForm">Edit</div>
</div>

<div class="">
<div v-show="!isEditing && exercise.done"> Completed</div>

<div v-show="!isEditing && !exercise.done"> Incomplete</div>

</div>
<div v-on:click="completeExercise(exercise)" v-show="!isEditing && !exercise.done">
Pending Exercises 
</div>

</div>
</div>

<div v-show="isEditing">
<div>
<label>Exercise Date</label>
<input type='text' v-model="exercise.date">
</div>
<div>
<label>Exercise</label>
<input type='text' v-model="exercise.title">
</div>
<div>
<label>Time</label>
<input type='text' v-model="exercise.time">
</div>
<div>
<label>Distance</label>
<input type='text' v-model="exercise.distance">
</div>
<div>
<label>Sets</label>
<input type='text' v-model="exercise.sets">
</div>
<div>
<label>Reps</label>
<input type='text' v-model="exercise.reps">
</div>
<div>
<label>Weight</label>
<input type='text' v-model="exercise.time">
</div>
<button v-on:click="hideForm"> Close X</button>
</div>



</div>

</template> 



<script type="text/javascript">
export default {
  props: ['exercise'],
data() {
    return {
        isEditing: false,
    }
},
methods: {
    completeExercise(exercise) {
        this.$emit('complete-exercise', exercise)
    },
    showForm() {
        this.isEditing = true
    }, 
    hideForm() {
        this.isEditing = false
    }, 
}, 



}


</script>



<style>

.e-container {
    border: 1px solid gray;
    width: 200px;
    margin: 20px;
}

.eEdit {
    padding: 30px; 
    font-size: 24px;
   
}

</style>