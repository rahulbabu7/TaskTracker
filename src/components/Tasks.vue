<template>
<div v-for="task in tasks" :key="task.id">
   <Task :task="task"/>

</div>

</template>

<script setup>
import { defineProps } from 'vue';
import Task from'./Task.vue'
defineProps({
    tasks:Array
})
</script>

<style scoped>

</style>