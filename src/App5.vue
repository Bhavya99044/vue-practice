
<!-- form data upload -->

<template>
  <pre>
    {{ JSON.stringify(form,null) }}
  </pre>
  <form>
    <div>
      <label for="name">Name:</label>
      <input type="text" v-model="form.name" required>

      <select id="select" v-model="form.country">
        <option v-for="(country,index) in countries" :value="country.value" :key="index">{{ country.value }}</option>
      </select>

      <label for="">
        <input type="checkbox" v-model="form.checkbox">
      </label>

      <label>multiple checkoute</label>
      <input type="checkbox" v-model="form.skillset" value="HTML"> HTML
      <input type="checkbox" v-model="form.skillset" value="CSS"> CSS
      <input type="checkbox" v-model="form.skillset" value="JavaScript"> JavaScript

      <label for="">
        <input type="radio" v-model="form.gender" value="male"> Male
      </label>


      <!-- v-model.trim -->
       use this for trim
       <!-- use v-model number for number falue store -->

       <!-- v-model.trim.lazy to to load data when usr click  -->

       <!-- @keyup.submit to submit the changes -->
    </div>
  </form>
  </template>
  <script>

    export default{
      data(){
        return {
          showAlert: false,
          countries: [
            {value: 'USA', label: 'USA'},
            {value: 'Canada', label: 'Canada'}
          ],
          form:{
            name:'',
            country:'',
            checkbox:false,
            skillset: []
          }
        }
      },
      methods: {
        toggleAlert() {
          this.showAlert =!this.showAlert;
        }
      }
    }

  </script>
