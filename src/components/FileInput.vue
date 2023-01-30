
    <!--  -->

<template>
    <input  
            type="file"
            name="file" 
            class="border-gray-300 border-[1px] focus:border-indigo-500 focus:ring-indigo-500 rounded-md shadow-sm"
            @input="$emit('update:modelValue', $event.target.files[0])"
            
            />



</template>

<script setup>


defineEmits(['update:modelValue']);

</script>