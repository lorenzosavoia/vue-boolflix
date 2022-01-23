<template>
  <header>
        <input type="text" v-model="textSearch">
        <button 
            type="submit"
            @click="getSearch();"
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
            queryStatic: 'https://api.themoviedb.org/3/search/',
            api_key:'517822c87cc8db164e77c94cc3efd137',
            
            objToPush:{
                movieFiltered: [],
                tvsFiltered:[],    
            },
              
        }
    },
    methods:{
        // getSearchValue(){
        //     return console.log(this.textSearch);
        // },
        getFilteredMovie(){
            const movie = 'movie';
            const parameters = {
                api_key: this.api_key,
                query: this.textSearch,
            };
            axios
                .get(`${this.queryStatic}${movie}`, {params:parameters})
                .then((result) =>{
                    this.movieFiltered = result.data.results;
                })
                .catch((error) => {console.log(error);})
        },
        getFilteredTvs(){
            const tv = 'tv';
            const parameters = {
                api_key: this.api_key,
                query: this.textSearch,
            };
            axios
                .get(`${this.queryStatic}${tv}`, {params:parameters})
                .then((result) =>{
                    this.objToPush.tvsFiltered = result.data.results;
                })
                .catch((error) => {console.log(error);})
        },
        getSearch(){
            this.getFilteredTvs();
            this.getFilteredMovie();
            this.uniqueArrayTvMovie =[...this.tvsFiltered, ...this.movieFiltered];
            this.$emit('doSearch', this.uniqueArrayTvMovie);
            // return [...this.movieAndTvs.tvsFiltered, ...this.movieAndTvs.movieFiltered]
            // this.$emit('doSearch', this.movieAndTvs)
            // console.log(this.movieAndTvs);
        }
        // getFilteredMovie(){
        //     this.query = this.queryStatic + this.textSearch
        //     console.log(this.query);
        //     axios
        //     .get(this.query)
        //     .then((results) => {
        //     this.movie = results.data.results;
        //     this.movie.forEach(element => {
        //         // console.log(element.title);
        //         this.movieFiltered.push(element)
                  
        //     });
        //     this.$emit('doSearch', this.movieFiltered);
            
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

<style>

</style>