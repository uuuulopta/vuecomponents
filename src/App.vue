
<template>
 
  

    <Tooltip id="tooltp" explains="el">Tooltip!</Tooltip>
    <div id="el" class="w-fit ml-20 mt-10 ">Hover for tooltip</div>
    <form id="upload" action="/files/upload" class="dropzone h-[50vh]">

    </form>
    <button @click="generateZip(file)" class="ml-2 rounded-md border-2 border-gray-300 shadow-sm px-1 bg-blue-200">Zip!</button>
</template>


<script setup>

import Tooltip from './components/Tooltip.vue';
import FileInput from './components/FileInput.vue';
import Zip from './components/Zip.vue';
import JSzip from "jszip"
import FileSaver from "file-saver";
import Dropzone from "dropzone";
import { onMounted } from 'vue';
let file;


function generateZip(file){
var zip = new JSzip();
zip.file("tetris.txt",file);
zip.generateAsync({type:"blob"})
.then(function (blob) {
    
}); 
}
onMounted( () => {
let myDropzone = new Dropzone("#upload");
myDropzone.on("addedfile", file => {
  console.log(`File added: ${file.name}`);
});


});



</script>