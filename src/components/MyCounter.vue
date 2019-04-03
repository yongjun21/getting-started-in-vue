<template>
  <div class="my-counter">
    <div>{{label}}</div>
    <div>{{count}}</div>
    <button @click="increment">+ {{label}}</button>
  </div>
</template>

<script>
export default {
  props: ['label'],
  data () {
    return {
      count: 1
    }
  },
  methods: {
    increment () {
      this.count++
      this.$emit('update', this.count)
    }
  }
}
</script>

<style>
button {
  font-size: inherit;
}
</style>
