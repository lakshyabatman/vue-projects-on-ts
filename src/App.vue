<template>
  <div id="app">
    <div id="nav">
      <router-link to="/todo">Todos</router-link> |
      <router-link to="/calculator">Calculator</router-link>
    </div>
    <router-view/>
    <Footer/>
  </div>
</template>

<script lang="ts">
import Footer from '@/components/Footer'
import {Vue, Component} from 'vue-property-decorator';

@Component({
  components: {
    Footer
  }
})
export default class App extends Vue{
  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin:0;
  padding: 0;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
