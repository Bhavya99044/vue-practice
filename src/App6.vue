<template>
  <p>{{ fullname }}</p>
  <button v-on:click="increment()">increment</button>
  <button v-on:click="decrement()">decrement</button>

  <p>Count: {{ count }}</p>
</template>

<script>

export default {
  data() {
    return {
      name: 'name',
      count: 0,
      lastName: 'lastName'
    }
  },
  methods: {
    increment() {
      this.count++
    },
    decrement() {
      this.count--
    }
  },
  //for calculate and join the data aftre merge
  // the need of computed properties is is any value change in the data then method will again and again called but in
  // but using computed only dependent value chnaged if depended name change
  computed: {
    fullname() {
      return this.name + '' + this.lastName;
    }
    // this is computed seeter method for get and set get will get data of this fllname
    // and using set we can set the variable value in data usin this.
    // fullname(){
    //   get(),
    //   set()
    // }
  },
  watch: {
    //
    count(oldValue, newValue) {
      if (newValue == '10') {
        alert(1)
      }
    },
    count:{
      immediate: true,
      handler(newValue, oldValue) {
        if (newValue == '10') {
          alert(2)
        }
      }
    }
    //deep watcher

  }
  //watcher will watch that data chage of variable and we can use that for alert if the condition true
  //we can use watcher similar to computed properties but not recommended
  //use watcher when you need compose new data from existing data source
  //the problem with watcher it only works on change of data not works when page reloads and input value existes
  //so we need for that immediate and deep watcher
}
</script>
