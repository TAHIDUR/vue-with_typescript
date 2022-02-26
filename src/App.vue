<script setup lang="ts">
import { ref, reactive, onMounted } from "vue";
import fetchCount from "./fetchCount";


interface AppInfo {
  name: string,
  slogan: string,
}

const count = ref<number | null>(null)

const info: AppInfo = reactive({
  name: 'Tuhin',
  slogan: 'Vue with Typescript',
})

onMounted(() => {
  fetchCount((initialCount) => {
    count.value = initialCount
  })
})

</script>

<template>
  <h1>{{ info.name }}</h1>
  <h2>{{ info.slogan }}</h2>
  <p>{{ count }}</p>
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
