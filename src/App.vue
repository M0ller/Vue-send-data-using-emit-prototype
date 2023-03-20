<template>
  <div class="divide">
    <div class="subDiv">
      <h1>Parent page</h1>
      <h2>Child State emit: {{ parentState }}</h2>
      <h2>Child Counter emit: {{ counterState }}</h2>
    </div>

    <div class="subDiv">
      <ChildComponent 
          @childStateChange="getState" 
          v-model:counter="counterState"
      />
    </div>
    
  </div>

</template>

<script>
import ChildComponent from "./components/ChildComponent.vue";

export default {
  components: {ChildComponent},
  data() {
    return {
      parentState: false,
      counterState: 0,
    }
  },
  methods: {
    getState(e) {
      this.parentState = e;
    }
  },
  computed: {}
}
</script>

<style scoped>

.divide {
  display: flex;
  flex-direction: row;
  column-gap: 20px;
}
.subDiv{
    border: 2px solid green;
  padding: 10px;
  }
</style>
