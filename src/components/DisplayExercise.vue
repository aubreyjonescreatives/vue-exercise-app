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

<div class="c-i">
<div v-on:click="showForm">Edit</div>
</div>

<div class="c-i" v-show="!isEditing && !exercise.done"> Incomplete</div>


<div class="c-i" v-show="!isEditing && exercise.done"> Completed</div>


<div class="c-i-p" v-on:click="completeExercise(exercise)" v-show="!isEditing && !exercise.done">
Mark as Complete 
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
    float: left; 
    display: inline-flex; 
    border: 1px solid gray;
    border-radius: 10px; 
    width: 25%;
    height: 100%;  
    margin: 20px;
}

.eInfo {
    padding: 10px; 
    font-size: 20px;
   
}

.c-i {
    border: 1px solid powderblue;
    border-radius: 10px; 
    display: inline-block; 
    background-color: powderblue; 
    width: 50%; 
    font-size: 15px; 
    padding: 7px;  
    margin: 5px; 
}





.c-i-p {
    border: 1px solid green;
    border-radius: 10px; 
    display: inline-block; 
    background-color: green; 
    color: white; 
    width: 100%; 
    font-size: 15px; 
    padding: 7px;  
    margin: 5px; 
}

</style>