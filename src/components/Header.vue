<template>
  <header>
        <input type="text" v-model="textSearch">
        <button 
            type="submit"
            @click="getFilteredMovie();"
        >
            Cerca
        </button>
  </header>
</template>

<script>
import axios from 'axios'
export default {
    name:'Header',
    data(){
        return{
            textSearch:'',
            queryStatic: 'https://api.themoviedb.org/3/search/movie?api_key=517822c87cc8db164e77c94cc3efd137&query=',
            // textSearch:'',
            query: '',
            movie: null,
            movieFiltered: [],
            
        }
    },
    methods:{
        getSearchValue(){
            return console.log(this.textSearch);
        },
        getFilteredMovie(){
            this.query = this.queryStatic + this.textSearch
            console.log(this.query);
            axios
            .get(this.query)
            .then((results) => {
            this.movie = results.data.results;
            this.movie.forEach(element => {
                // console.log(element.title);
                this.movieFiltered.push(element)
                  
            });
            this.$emit('doSearch', this.movieFiltered);
            
            })
            .catch((error) => console.log(error));

            console.log(this.movieFiltered);
            return this.movieFiltered
        },
        getAllert(){
            return console.log('ciao');
        }
    },
}
</script>

<style>

</style>