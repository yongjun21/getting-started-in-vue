<template>
  <div id="app">
    <my-counter :label="labelA" @update="stateA = $event"></my-counter>
    <div> X </div>
    <my-counter :label="labelB" @update="stateB = $event"></my-counter>
    <div> = </div>
    <my-result>{{result}}</my-result>
  </div>
</template>

<script>
import MyCounter from './components/MyCounter.vue'
import MyResult from './components/MyResult.vue'

export default {
  name: 'app',
  components: {
    MyCounter,
    MyResult
  },
  data () {
    return {
      labelA: 'A',
      labelB: 'B',
      stateA: 1,
      stateB: 1
    }
  },
  computed: {
    result () {
      return this.stateA * this.stateB
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  font-size: 36px;

  display: flex;
  justify-content: center;
  align-items: center;

  & > div + div {
    margin-left: 30px;
  }
}
</style>
