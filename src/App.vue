<script setup lang="ts">
import { reactive } from "vue";


interface AppInfo {
  name: string,
  slogan: string,
}


// const nextCount = computed(() => {
//   if(count.value !== null)
//   {
//     return count.value + 1
//   }

//   return null
// })


const info: AppInfo = reactive({
  name: 'Tuhin',
  slogan: 'Vue with Typescript',
})

</script>

<template>
  <h1>{{ info.name }}</h1>
  <h2>{{ info.slogan }}</h2>

  
  <Counter
    :limit="10"
  ></Counter>

<!--   optional message
  <Counter
    :limit="10"
    :alert-message-on-limit="'counting limit can not be crossed'"
  ></Counter> -->
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
