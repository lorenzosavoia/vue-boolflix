<template>
  <div id="app">
    <Header @doSearch="search($event)"></Header>
    <Main :uniqueArrayTvMovie="tvAndMovie"> </Main>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
  data(){
    return{
      tvAndMovie: {
        movie: null,
        tvs: null,
      }
    }
  },
  methods:{
    search(value) {
      this.uniqueArrayTvMovie = value;
    }
  }
}
</script>

<style lang="scss">
#app {
 
}
</style>
