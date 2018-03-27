<template>
  <div id="app">
    <div id="nav">
      <img src="./assets/Marvel-Logo.png">
    </div>
    <List/>
  </div>
</template>

<script>
import List from './components/List'

export default {
  name: 'App',
  components: {
    List
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
  background-color: #f1f2f0;
}
#nav{
  background-color: #e92227;
  height: 90px;
}
img{
  width: 20%;
  border: 5px solid white;
  margin-top: 10px;
}
</style>
