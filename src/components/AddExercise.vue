<template>
<div id="exercise-form">
<form @submit.prevent="handleSubmit">
<label>Exercise Item</label>
<input v-model="item.name" type="text" />
<label>Item Amount</label>
<label v-model="item.amount" type="number" /> 
<button>Add Item</button>
</form>

</template> 



<script>
export default {
    name: 'exercise-form', 
    data() {
        return {
            item: {
                name: '', 
                amount: ''
            }
        }
    }, 
    methods: {
        handleSubmit() {
            console.log('submitting')
        }
    }
}


</script>



<style>



</style>