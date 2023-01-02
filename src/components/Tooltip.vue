<template>
    <div :id="id" data-show="false" role="tooltip" :style="style" @mouseover="hover"
    class="absolute z-10 py-1 px-3 text-xs font-medium text-white bg-gray-900 rounded-lg shadow-sm opacity-0 transition-opacity duration-300 dark:bg-gray-700">
    <div ref="slot"><slot></slot></div>
</div>

</template>

<style>


</style>

<script setup>
import {onMounted, ref,} from 'vue';
import { createPopper } from '@popperjs/core';
const props = defineProps({
    id: {
        type: String,
    },
    explains:{
        type: String,
    },
});
let slot = ref();

onMounted( () => {
const tooltip = document.getElementById(props.id);
const target = document.getElementById(props.explains);
const popper = createPopper(target,tooltip, {
    placement: 'top',

});


target.addEventListener('mouseover', () => {
    tooltip.style = "opacity:1;"
    popper.update();
})
target.addEventListener('mouseout', () => {
    tooltip.style = "opacity:0;"
    popper.update();
})


})





</script>