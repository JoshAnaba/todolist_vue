<template>
  <div id="app">
   <Header/>
    <router-view/>
  </div>
</template>

<script>
import Header from './components/layout/Header'
export default {
  name: 'App',
  components:{
    Header
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;

}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #375a7d;

    &.router-link-exact-active {
      color: white;
    }
  }
}
</style>
