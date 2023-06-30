<template>
  <div :class="[task.reminder ? 'reminder' : ' ','task']">
    <h3>
      {{ task.text }}
      <i @click="onDelete(task.id)" class="fas fa-times"></i>
    </h3>
    
    <p>{{ task.day }}</p>
  </div>
</template>

<script setup>
import { defineProps, getCurrentInstance } from "vue";

const props = defineProps({
  task: Object,
});

const onDelete = (id) => {
  const instance = getCurrentInstance();
  if (instance) {
    instance.emit("delete-task", id); // Emit the custom event with the 'id' as payload
  }
};
</script>

<style scoped>
.fas{
    color: red;
}
div {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
}

.task.reminder {
  border-left: 5px solid green;
}

.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
