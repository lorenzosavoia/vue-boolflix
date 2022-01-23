<template>
  <main>
    <Card  
        v-for="(movie, index) in tvAndMovie.movie"
        :key="'movie'+ index"
        :title="movie.title"
        :original="movie.original_title" 
        :language="movie.original_language"
        :vote="movie.vote_average"
        :poster="movie.poster_path"
        :cover="movie.overview"
        :image="`https://image.tmdb.org/t/p/w342${movie.poster_path}`"
    > 
    </Card>
    <Card  
        v-for="(tvs, index) in tvAndMovie.tvs"
        :key="'tv'+ index"
        :title="tvs.name"
        :original="tvs.original_name" 
        :language="tvs.original_language"
        :vote="tvs.vote_average"
        :poster="tvs.poster_path"
        :cover="tvs.overview"
        :image="`https://image.tmdb.org/t/p/w342${tvs.poster_path}`"
    > 
    </Card>
    
  </main>
</template>

<script>
// import axios from "axios";
import Card from "./Card.vue"

export default {
    name: 'Main',
    props: ["tvAndMovie"],

    data(){
        return{
            // queryStatic: 'https://api.themoviedb.org/3/search/movie?api_key=517822c87cc8db164e77c94cc3efd137&query=batman',
            // textSearch:'',
            // query: '',
            // movieFiltered: [],
            // movie: null,
            
        };
    },
    components: {
        Card,
    },
    computed: {
    //   filterMovie() {

    //   }  
    },
    created(){
        // axios
        // .get(this.query)
        // .then((results) => {
        //     this.movie = results.data.results;
        //     console.log(this.movie);
        //     this.movie.forEach(element => {
        //         // console.log(element.title);
        //         this.movieFiltered.push(element)
                
        //     });
            
        // })
        // .catch((error) => console.log(error));

        // console.log(this.movieFiltered);
        // console.log(this.movieFiltered);
    },
    methods:{
        // getFilteredMovie(){
        //     // this.query = this.queryStatic + this.textSearch
        //     // console.log(query);
        //     axios
        //     .get(this.queryStatic)
        //     .then((results) => {
        //     this.movie = results.data.results;
        //     this.movie.forEach(element => {
        //         // console.log(element.title);
        //         this.movieFiltered.push(element)
                  
        //     });
            
        //     })
        //     .catch((error) => console.log(error));

        //     console.log(this.movieFiltered);
        //     return this.movieFiltered
        // },
        // getAllert(){
        //     return console.log('ciao');
        // }
    },
}
</script>

<style lang='scss'>

</style>