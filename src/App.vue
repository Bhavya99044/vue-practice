<script>
  export default{
    data(){
      return{
        message:'hello world',
        status:'inactive',
        tasks:['one', 'two', 'three'],
        link:'http://google.com'
      }
    },
    methods:{
      toggleStatus(){
        this.status = this.status === 'active'? 'inactive' : 'active'
      }
    }
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