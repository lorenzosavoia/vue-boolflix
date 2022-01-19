<template>
  <main>
      <button type="sumbit" 
        @click="getFilteredMovie(); getAllert();"
        
        >

      </button>
    <ul
        v-for="(element, index) in movieFiltered"
        :key="'A'+ index"
    >
        <li>{{element.title}}</li>    
        <li>{{element.original_title}}</li>    
        <li>{{element.original_language}}</li>    
        <li>{{element.vote_count}}</li>    
    </ul> 
  </main>
</template>

<script>
import axios from "axios";

export default {
    name: 'Main',
    
    data(){
        return{
            queryStatic: 'https://api.themoviedb.org/3/search/movie?api_key=517822c87cc8db164e77c94cc3efd137&query=batman',
            textSearch:'',
            query: '',
            movie: null,
            movieFiltered: [],
            
        };
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
    },
    methods:{
        getFilteredMovie(){
            // this.query = this.queryStatic + this.textSearch
            // console.log(query);
            axios
            .get(this.queryStatic)
            .then((results) => {
            this.movie = results.data.results;
            this.movie.forEach(element => {
                // console.log(element.title);
                this.movieFiltered.push(element)
                  
            });
            
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