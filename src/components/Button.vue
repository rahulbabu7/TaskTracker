<template>
<button @click="onClick()" v-bind:style="{background: color}" class="btn">
    {{ text }}
</button>
</template>

<script setup>
import { defineProps } from 'vue';
defineProps({
    text:String,
    color:String
})
//without using arrow functions
/*
function onClick(){
    console.log("Clicked")
}
*/
//With arrow functions
const onClick = ()=>{
    console.log("Clicked")
}
</script>

<style scoped>
</style>