<template>
  <div>
      <h2>-------- Watcher -----------</h2>
      <h3>Current Volume - {{ volume }}</h3>
      <div>
          <button @click="volume +=2">Increase</button>
          <button @click="volume -=2">Decrease</button>
      </div>
    <input type="text" v-model="movie">
    <input type="text" v-model="movieInfo.title" placeholder="movie title">
    <input type="text" v-model="movieInfo.actor" placeholder="movie actor">  
    <div>
        <button @click="movieList = movieList.concat(['Winder Woman'])">Add Movie</button>
    </div>      
  </div>
</template>

<script>
export default {
    data(){
        return {
            volume: 0,
            movie: 'Batman',
            movieInfo: {title: '', actor: ''},
            movieList: ['Batman', 'Superman']
        }
    },
    methods: {},
    computed: {},
    watch: {
        volume(newValue, oldValue){
            if(newValue > oldValue && newValue === 16){
                alert('High Volume!')
            }
        },
        movie:{
            handler(newValue){
                console.log(`Calling API with movie name = ${newValue}`)
            },
            immediate: true,
        },
        movieInfo: {
            handler(newValue){
                console.log(
                `Calling API movie title = ${newValue.title} and actor = ${newValue.actor}`
                )
            },
            deep: true
        },
        movieList:{
            handler(newValue){
                console.log(`Updated List: ${newValue}`)
            }
        }
    }
}
</script>

<style scoped>
    button{
        padding: 10px;
        margin: 15px;
    }
</style>