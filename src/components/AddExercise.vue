<template>

<div>
<button class="addButton" v-on:click="openForm" v-show="!isCreating">+ EXERCISE</button>

<div v-show="isCreating">
<div>
<label>Exercise Date</label>
<input v-model="dateText" type='text' ref='title' defaultValue="">
</div>
<div>
<label>Exercise Title</label>
<input v-model="titleText" type='text' ref='title' defaultValue="">
</div>
<div>
<label>Exercise Time</label>
<input v-model="timeText" type='text' ref='title' defaultValue="">
</div>
<div>
<label>Exercise Distance</label>
<input v-model="distanceText" type='text' ref='title' defaultValue="">
</div>
<div>
<label>Exercise Sets</label>
<input v-model="setText" type='text' ref='title' defaultValue="">
</div>
<div>
<label>Exercise Reps</label>
<input v-model="repsText" type='text' ref='title' defaultValue="">
</div>
<div>
<label>Exercise Weight</label>
<input v-model="weightText" type='text' ref='title' defaultValue="">
</div>
<div>
<button v-on:click="sendForm()">Create</button>
<button v-on:click="closeForm()">Cancel</button>
</div>
</div>
</div>

</template> 



<script>
export default {
 
 
data() {
    return {
        dateText: '',
        titleText: '', 
        timeText: '',
        distanceText: '',
        setText: '',
        repsText: '', 
        weightText: '', 
        isCreating: false,
    };
},
methods: {
    openForm() {
        this.isCreating = true
    }, 
    closeForm() {
        this.isCreating = false
    }, 
    sendForm() {
        if (this.titleText.length > 0) {
            const date = this.dateText; 
            const title = this.titleText; 
            const time = this.timeText; 
            const distance = this.distanceText; 
            const set = this.setText; 
            const reps = this.repsText; 
            const weight = this.weightText; 
            this.$emit('add-exercise', {
                date,
                title, 
                time, 
                distance, 
                set, 
                reps, 
                weight,
                done: false,
            })
            this.titleText = '';
        }
        this.isCreating = false;
    }
}, 



}


</script>



<style>


.addButton {
    display: block; 
    clear: both; 
    width: 200px; 
    text-align: center; 
    padding: 10px;
    background-color: darkblue; 
    color: white; 
    border: none; 
    border-radius: 10px;  
}


</style>