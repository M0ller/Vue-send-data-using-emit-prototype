<template>
<h1>Child Component</h1>
  <h2>State: {{childState}}</h2>
  <button @click="changeChildState">
    Change child state
  </button>
  
  <h2>Child Counter: {{ this.childCounter }}</h2>
  <button @click="addNumber">
    increment child counter
  </button>
</template>

<script>
export default {
name: "ChildComponent",
  data() {
    return {
      childCounter: 0,
      childState: false,
    }
  },
  methods: {
    changeChildState() {
      this.childState = !this.childState;
      this.$emit('childStateChange', this.childState);
    },
    addNumber(){
      this.childCounter ++;
      this.$emit('update:counter', this.childCounter);
    }
  },
}
</script>

<style scoped>

</style>