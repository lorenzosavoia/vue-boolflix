<template>
  <div id="app">
    <Header @doSearch="search($event)"></Header>
    <Main :tvAndMovie="tvAndMovie"> </Main>
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
      this.tvAndMovie.movie = value.movieFiltered;
      this.tvAndMovie.tvs= value.tvsFiltered;
      console.log(this.tvAndMovie);
    }
  }
}
</script>

<style lang="scss">
#app {
 
}
</style>
