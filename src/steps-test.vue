<template>
  <div>
    <steps :count="count" :active="active"></steps>
    <button @click="next">下一步</button>
  </div>
</template>

<script>
import Steps from './step.vue'

export default {
  components: {
    Steps
  },
  data () {
    return {
      count: 4,
      active: 1
    }
  },
  methods: {
    next(){
      this.active++
    }
  }
}
</script>

<style>

</style>