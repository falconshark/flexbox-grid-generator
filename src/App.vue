<template>
  <div id="app">
    <h1 class="website-header">Flexbox Grid Generator</h1>
    <div class="desc">
      Get Flexbox layout CSS code which base on Bootstrap 4 for reference.
    </div>
    <Flexbox/>
  </div>
</template>

<script>
import Flexbox from './components/Flexbox'

export default {
  name: 'App',
  components: {
    Flexbox
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.website-header{
  margin-top: 60px;
}
.desc{
  margin-bottom: 60px;
}
</style>
