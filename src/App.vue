<template>
  <div id="app">
    <div class="header--wrapper">
      <img alt="Vue logo" src="./assets/logo.png">
      <span class="header--text">Custom Events</span>
    </div>
    <ParentComponent />
  </div>
</template>

<script>
import ParentComponent from './components/parent-component/ParentComponent'

export default {
  name: 'app',
  components: {
    ParentComponent
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
  margin-top: 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.header--wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 2rem;
}
.header--text {
  font-size: 5rem;
}
</style>
