<template>
    <header>
        <h1> {{ title }}</h1>
        <Button text="Add Task" color='green'/>
    </header>
 
</template>

<script setup>
import { defineProps } from 'vue';

defineProps({
    title:String,
})
import Button from './Button.vue'
</script>

<style scoped>
header{
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
}

</style>


  
