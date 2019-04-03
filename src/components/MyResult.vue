<template>
  <div class="my-result">
    <div class="inner-div" :style="{opacity: visible ? 1 : 0}">
      <slot></slot>
    </div>
  </div>
</template>

<script>
import { setTimeout } from 'timers';
export default {
  data () {
    return {
      visible: false
    }
  },
  created () {
    this.blink()
  },
  methods: {
    blink () {
      this.visible = !this.visible
      setTimeout(this.blink, this.visible ? 1500 : 500)
    }
  }
}
</script>

<style>
.inner-div {
  transition: opacity 0.5s;
}
</style>
