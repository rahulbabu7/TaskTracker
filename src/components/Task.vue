<template>
  <div @dblclick="$emit('toggle-reminder')" :class="[task.reminder ? 'reminder' : ' ','task']">
    <h3>
      {{ task.text }}
      <!-- <i @click="$emit('onDelete',task.id)" class="fas fa-times"></i> -->
      <i @click="deleted(task.id)" class="fas fa-times"></i>
    </h3>
    
    <p>{{ task.day }}</p>
  </div>
</template>

<script setup>
import { defineProps} from "vue";
 defineProps({
  task: Object,
});
/*emit in script*/

const emit = defineEmits(['onDelete','toggle-reminder'])

const deleted = (id)=>{
emit('onDelete',id)
}
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
