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
      object:{
        backgroundColor:'yellow',
        padding:10+'px'
      }
    }
  }
}
</script>

<style scoped>
  .color{
    color:red;
  }
</style>