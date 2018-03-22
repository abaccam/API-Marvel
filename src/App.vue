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
  background-image: url("./assets/marvel-background.jpg");
}
#nav{
  background-color: rgba(0, 0, 0, 0.9);
  height: 130px;
}
img{
  width: 20%;
  border: 5px solid white;
  margin-top: 10px;
}
</style>
