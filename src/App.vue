<script setup lang="ts">
import { reactive, ref, onMounted } from "vue";
import addButton from "./components/addButtons.vue";


interface AppInfo {
  name: string,
  slogan: string,
}


interface Props {
    limit: number;
    alertMessageOnLimit?: string;
}

const props = withDefaults(defineProps<Props>(),{
    alertMessageOnLimit: 'can not go higher'
})
// const nextCount = computed(() => {
//   if(count.value !== null)
//   {
//     return count.value + 1
//   }

//   return null
// })

const count = ref<number | null>(null)

function addCount(num: number) {
  if (count.value !== null) {
    if (count.value >= props.limit) {
      alert(props.alertMessageOnLimit)
    }
    else {
      count.value += num
    }
  }
}

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

  <p>Count: {{ count }}</p>

  <addButton>
    @add-count="addCount"
    @reset-count="count = 0"
  </addButton>
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
