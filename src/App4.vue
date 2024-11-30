<template>
<h1>{{ fullName }}</h1>
</template>

<script>

export default{
  data(){
    return {
      name:'name',
      lastName:'lastName'
    }
  },
  //for calculate and join the data aftre merge
  // the need of computed properties is is any value change in the data then method will again and again called but in
  // but using computed only dependent value chnaged if depended name change
  computed:{
    fullName(){
      return this.name +' '+ this.lastName
    }
  }

}
</script>

