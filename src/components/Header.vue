<template>
  <header>
        <input type="text" v-model="textSearch">
        <button 
            type="submit"
            @click="$emit('musicSearch', textSearch); getSearchValue();"
        >
            Cerca
        </button>
  </header>
</template>

<script>
export default {
    name:'Header',
    data(){
        return{
            textSearch:'',
            
        }
    },
    methods:{
        getSearchValue(){
            return console.log(this.textSearch);
        }
    },
}
</script>

<style>

</style>