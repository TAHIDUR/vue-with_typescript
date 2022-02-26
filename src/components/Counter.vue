<script setup lang="ts">
import { ref, onMounted } from "vue";
import fetchCount from "../fetchCount";



const emit = defineEmits<{ 
  (event: 'add-count', num: number): void  
  (event: 'reset-count'): void 
}>()

interface Props {
    limit: number;
    alertMessageOnLimit?: string;
}

const props = withDefaults(defineProps<Props>(),{
    alertMessageOnLimit: 'can not go higher'
})


const count = ref<number | null>(null)


onMounted(() => {
  fetchCount((initialCount) => {
    count.value = initialCount
  })
})



</script>


<template>
    <div>
<!--   
        <p>{{ count }}</p>

        <p>

            <button @click="addCount(1)">Add</button>
            <button @click="emit('add-count', 1)">Add</button> -->
            <!-- <button @click="emit('reset-count')">Reset</button> -->
        <!-- </p> --> 
    </div>
</template>