<template>
    <header>
        <h1> {{ title }}</h1>
    </header>
 
</template>

<script setup>
import { defineProps } from 'vue';

defineProps({
    title:string,
})
</script>

<style scoped>
header{
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
}

</style>


  
