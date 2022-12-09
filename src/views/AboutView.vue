<script setup lang="ts">
import {ref, onMounted} from 'vue'
import {useCounterStore} from '../stores/counter'

const counter = useCounterStore()

let count = ref(0)

const increment = () => count.value++

onMounted(() => {
  console.log(`initial count ${count.value}`, counter)
})


</script>


<template>
  <div class="about">
    <h1>This is an about page</h1>
    <button @click="increment">count is {{count}}</button>
    <button @click="counter.increment">counter is {{counter.count}}</button>
    <button>{{counter.doubleCount}}</button>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>

