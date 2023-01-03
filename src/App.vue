
<template>
 
  

    
    <Tooltip id="tooltp" explains="el">Tooltip!</Tooltip>
    <div id="el" class="w-fit ml-20 mt-10 ">Hover for tooltip</div>
    <FileInput v-model="file"></FileInput>


</template>


<script setup>

import Tooltip from './components/Tooltip.vue';
import FileInput from './components/FileInput.vue';

let file = ""
</script>