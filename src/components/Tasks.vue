<template>
<div v-for="task in tasks" :key="task.id">
   <Task @delete-task="del(task.id)" :task="task"/>

</div>

</template>

<script setup>
import { defineProps, getCurrentInstance } from "vue";
import { defineEmits } from 'vue';
import Task from'./Task.vue'
defineProps({
    tasks:Array
})

defineEmits(['delete-task']);
const del= (id) => {
  const instance = getCurrentInstance();
  if (instance) {
    instance.emit("del", id); // Emit the custom event with the 'id' as payload
  }
};
</script>

<style scoped>

</style>