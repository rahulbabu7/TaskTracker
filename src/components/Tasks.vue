<template>
<div v-for="task in tasks" :key="task.id">
   <!-- <Task :task="task" @on-Delete="$emit('deleteTask',task.id)" /> -->
   <Task  @toggle-reminder="$emit('toggle-reminder',task.id)" :task="task" @onDelete="deleteTask" />

</div>

</template>

<script setup>
import { defineProps} from "vue";
import Task from'./Task.vue'
defineProps({
    tasks:Array
})

const emit = defineEmits(['deleteTask','toggle-reminder'])
const deleteTask = (id)=>{
  emit('deleteTask',id)
}

</script>

<style scoped>

</style>