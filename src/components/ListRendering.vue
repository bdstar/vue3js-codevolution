<template>
    <!--
        url: https://vuejs.org/v2/guide/list.html
        v-for Directive:-
        Array of String
        Array of Object
        Array of Array
        Block of HTML Elements
        Object key value pairs
    -->
  <div>
      <h2>{{ text }}</h2>

      <!--Array of String-->
      <h2 v-for="(name, index) in names" :key="name">{{index}} - {{ name }}</h2>
  
      <!--Array of Object-->
      <h2 v-for="name in fullNames" :key="name.first">{{name.first}} {{name.last}}</h2>

      <!--Array of Array-->
      <div v-for="actor in actors" :key="actor.name">
          <h2>{{actor.name}}</h2>
          <h3 v-for="movie in actor.movies" :key="movie">{{movie}}</h3>
      </div>

      <hr>
      <!-- Block of HTML Elements -->       
      <!--<template v-for="(item, index) in items">
        <span :key="index"></span>
      </template>-->

      <!-- Object key value pairs -->      
      <h2 v-for="(value, key, index) in myInfo" :key="value">{{index}} {{key}} {{value}}</h2>

  </div>
</template>

<script>
export default {
    name: 'ListRendering',
    data(){
        return{
            text: "--------- List Rendering ------------",
            names: ['Bruce', 'Clark', 'Diana'],
            items: [
            { message: 'Foo' },
            { message: 'Bar' }
            ],            
            myInfo: {
                name: 'Vishwas',
                channel: 'Codevolution',
                course: 'Vue 3'
            },            
            fullNames: [
                { first: 'Bruce', last: 'Wayne'},
                { first: 'Clark', last: 'Kent'},
                { first: 'Princess', last: 'Diana'},
            ],
            actors: [
                {
                    name: 'Christian Bale',
                    movies: ['Batman', 'The Prestige'],
                },
                {
                    name: 'Di Caprio',
                    movies: ['Titanic', 'Inception']
                }
            ],
        }
    }
}
</script>

<style>

</style>