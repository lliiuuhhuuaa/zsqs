<template>
  <div id="app">
    <WebHeader msg="message header" />
    <WebBody msg="message body"/>
  </div>
</template>

<script>
import WebHeader from './components/WebHeader.vue'
import WebBody from './components/WebBody.vue'

export default {
  name: 'App',
  components: {
    WebHeader:WebHeader,
    WebBody:WebBody
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background: #FFF;
}
</style>
