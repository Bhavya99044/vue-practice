<script setup>
import { ref } from 'vue';
        const status = ref('active');
        const tasks = ref(['task1', 'task2', 'task3']);
        const link = ref('https://www.google.com');
        const toggleStatus = () => {
            status.value = status.value === 'active'? 'inactive' : 'active';

       
    
  
  }
</script>

<template>
  <!-- option api -->
  <!-- /If statement option api -->
  <h1 v-if="status === 'active'">hello</h1>
  <h1 v-else-if="status === 'inactive'">bye</h1>
  <h1 v-else>deactive</h1>

  <!-- for loop -->
  <ul>
    <li v-for ="task in tasks" :key="task">{{ task }}</li>
  </ul>

  <!-- link tag -->
  <a v-bind:href="link" _blank>click</a>
  <a :href="link" _blank>click</a>

  <!-- toggle button -->    
   <button @click="toggleStatus">{{ status }}</button>

</template>

<style scoped>
h1{
  color: red;
}</style>