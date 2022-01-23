<template>
  <div class="card">
       <ul> 
        <li>{{title}}</li>    
        <li>{{original}}</li>    
        <li>{{language}}</li>    
        <li>{{vote}}</li>
        <li><img :src="image" alt=""></li> 
     </ul>  
  </div>
</template>

<script>
export default {
    name: 'Card',
    props: [
        'title',
        'image',
        'original',
        'language',
        'vote',
        'poster',
        'cover',
        'id',
        'type',
    ],

}
</script>

<style lang="scss">

</style>