<template>
  <div>
      <h2>--------- Event Handling ----------</h2>
      <h2 v-once>Name(once Directive): {{name}}</h2>
      <h2 v-pre>Name(pre Directive): {{name}}</h2>
      <h2>Name: {{name}}</h2>

      <button v-on:mouseover="name = 'Batman'">Change Name: </button>
      <button @click="name ='Superman'">Change Name: Superman</button>
      <button v-on:click="changeName('Mamun', $event), increment(2)">Change Name to Mamun </button>

      <h2>Total Click: {{count}}</h2>
      <button v-on:click="count += 1">Increment</button>
      <button v-on:click="count -= 1">Decrement</button> 

      <h2>Total Click: {{iteration}}</h2>
      <button v-on:click="increment(2)">Increment 2</button>
      <button v-on:click="decrement(2)">Decrement 2</button> 
      <button @click="increment(5)">Increment 5</button>
      <button @click="decrement(5)">Decrement 5</button>                  
  </div>
</template>

<script>
export default {
  name: 'EventHandling',
  data() {
    return{
        name: "Adam",
        count: 0,
        iteration: 0
    }
  },
  methods:{
      changeName(cname, event){
          this.name = cname;
          console.log(event);
      },
      increment(num){
          this.iteration += num;
      },
      decrement(num){
          if(this.iteration<=0){
            this.iteration = 0;
          }else{
            this.iteration -= num;
          }
      }
  }
}
</script>

<style scoped>
    button{
        padding: 5px;
        margin: 10px;
    }
</style>