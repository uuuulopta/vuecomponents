<template>
    <div :id="id" role="tooltip" :style="style"
    :class="tooltipClass">
    <slot></slot>
</div>

</template>

<style>


</style>

<script setup>
import {onMounted, ref} from 'vue';

const props = defineProps({
    id: {
        type: String,
    },
    explains:{
        type: String,
    },
});
let tooltipClass = ref("absolute z-10 py-2 px-3 text-sm font-medium text-white bg-gray-900 rounded-lg shadow-sm opacity-100 transition-opacity duration-300 dark:bg-gray-700")
let style=ref("");
onMounted(() => {
const el = document.getElementById(props.explains).getBoundingClientRect()
const tooltip = document.getElementById(props.id).getBoundingClientRect()
style.value = `top:${el.y - 35}px;left:${el.x -  tooltip.width * 1/3}px;`


})



</script>