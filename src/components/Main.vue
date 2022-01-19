<template>
  <main>
     
  </main>
</template>

<script>
import axios from "axios";

export default {
    name: 'Main',
    
    data(){
        return{
            query: 'https://api.themoviedb.org/3/search/movie?api_key=517822c87cc8db164e77c94cc3efd137&query=batman',
            movie: null,
            movieFiltered: [],
        };
    },
    computed: {
    //   filterMovie() {

    //   }  
    },
    created(){
        axios
        .get(this.query)
        .then((results) => {
            this.movie = results.data.results;
            console.log(this.movie);
            this.movie.forEach(element => {
                // console.log(element.title);
                this.movieFiltered.push(element.title)
                
            });
            
        })
        .catch((error) => console.log(error));

        console.log(this.movieFiltered);
    }
}
</script>

<style>

</style>