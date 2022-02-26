<script setup lang="ts">

const emitTest = defineEmits<{ 
  (event: 'add-count', num: number): void  
  (event: 'reset-count'): void 
}>()

</script>

<template>
  <p>
    <button @click="emitTest('add-count', 1)">Add</button>
    <br>
    <br>
    <button @click="emitTest('reset-count')">Reset</button>
  </p>
</template>