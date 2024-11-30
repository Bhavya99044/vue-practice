<template>
{{ name }}
<!-- v-text -->
<div v-text="name"></div>

 <!-- html binding -->
  <div v-html="hack"></div>

  <!-- id binding -->
   <div :id="dataId">bhjbjhn</div>

   <!-- button diable -->
    <button :disabled="isDisabled" :class="isDisabled&&color">Submit</button>

    <!-- binding css with condition -->
  <div :class="isDisabled&&color">bhavya</div>

  <!-- dont use above use tenary operation1 also array can be applied of class
    -->
    <div :class="isDisabled?'color':''">nnnn</div>

    <!-- binding styles object and array -->
    <!-- v-show directives -->
     <!-- difference between v-show and v-if show display none and second is not show div tag -->
    <div v-show="isDisabled" :style="red">red</div>

    <h2>{{object.padding}}</h2>


    <!-- if you want to use v-for and v-if for codition -->
     <div v-for="item in items" :key="item.id" >
      <div v-if="item.name === 'bhavya'">
       {{item.id}}
      </div>
     </div>

     <!-- methods in view -->
     <h1>bhavya count {{ add() }}</h1>

     <!-- on hover same we can use click for that -->
     <button v-on:mouseover="SubmitEvent()">click</button>
     <h1>{{ count }}</h1>

<!-- add multiple events using coma -->
<button @click="changeEvent(data)">change event</button>
</template>

<script>

export default {
  data(){
    return{
      isDisabled:false,
      name:'bhavya',
      hack:"<b>bhavya</b>",
      dataId:'bbbb',
      color:'color',
      red:{
      color:'green',
      fontSize:90+'px'
      },
      items:[
        {id:1,name:'bhavya'},
        {id:2,name:'bhavya'},
        {id:3,name:'bhavya'},
        {id:4,name:'bhavya'}
        ],
      bhavya:'bhavya',  // to use v-if condition in v-for loop we need to define it as a variable and use it in v-if condition.
      object:{
        backgroundColor:'yellow',
        padding:10+'px'
      },
      count:0
    }
  },
  // methods
  methods:{
     add(){
      return 1+2+3;
    },
    SubmitEvent(){
      this.count++;
    },
    changeEvent(event){
      console.log(event)
    }
  }
}
</script>

<style scoped>
  .color{
    color:red;
  }
</style>
