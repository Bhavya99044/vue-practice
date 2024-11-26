<script setup>
import { ref,onMounted } from 'vue';
const status = ref('active');
const tasks = ref(['task1', 'task2', 'task3']);
const link = ref('https://www.google.com');
const newTask=ref('');
const toggleStatus = () => {
  status.value = status.value === 'active' ? 'inactive' : 'active';
}

const inputText='hello';

// form submition handler
const submitForm = () => {
    if(newTask.value.trim()!=''){
      // console.log(newTask)
      tasks.value.push(newTask.value);
      console.log(tasks.value)
    }
  }

  // delete task logic
  const deleteTask=(id) => {
    tasks.value.splice(id, 1);
  }

  onMounted(async()=>{
    try{
      const response=await fetch('https://dummyjson.com/products')
      const data=await response.json();
      
   tasks.value=data.products.map((task)=>{
   return  task.title})
    }
    catch{

    }
  });

</script>

<template>
  <!-- option api -->
  <!-- /If statement option api -->
  <h1 v-if="status === 'active'">hello</h1>
  <h1 v-else-if="status === 'inactive'">bye</h1>
  <h1 v-else>deactive</h1>

  <!-- for loop -->
  <ul>
    <li v-for="(task,index) in tasks" :key="task">{{ task }}
      <button @click="deleteTask(index)">delete</button>
    </li>
  </ul>

  <!-- link tag -->
  <a v-bind:href="link" _blank>click</a>
  <a :href="link" _blank>click</a>

  <!-- toggle button -->
  <button @click="toggleStatus">{{ status }}</button>


  <!-- form -->
  <form @submit.prevent="submitForm">
    <input type="text" name="newTask" v-model="newTask">
    <button type="submit">Submit</button>
  </form>
</template>

<style scoped>
h1 {
  color: red;
}
</style>