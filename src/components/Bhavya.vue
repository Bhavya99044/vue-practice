<!-- vbase shortcut for vue design -->
<script>
export default {
  //we can pass prop here of component
  // props:['name']

  // datatype in props so developer can know what should pass or not
  props: {
    name: {
      type: String,//without type field normal variable jode pan chalse
      required: true, //this means name is required, otherwise it will throw error
    }
  },
}
</script>

<template>
  <div>
    <h1>hello {{ name }}</h1>
    <!-- we can specify for attributes  to apply id on that -->
    <h2 v-bind="$attrs">bahvay</h2>
  </div>
</template>

<style lang="scss" scoped></style>
