<template>
<div id="exerciseList-table">
<table>
<thead>
<tr>
<th>Item</th>
<th>Amount</th>
</tr>
</thead>
<tbody>
<tr v-for="item in items" :key="item.id">
<td>{{ item.name }}</td>
<td> {{ item.amount }}</td>
</tr>
</tbody>
</table>
</div>
</template>



<script>

export default {
    name: 'ExerciseList', 
    props: {
        items: Array 
    }


}

</script>


<style scoped>


</style>