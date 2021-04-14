<template>
    <div class="conditional-component">
        <h2 v-if="num === 0">The number is zero</h2>
        <h2 v-else-if="num < 0">The number is negative</h2>
        <h2 v-else-if="num > 0">The number is negative</h2>
        <h2 v-else>The number is not zero</h2>
        <div v-if="display">
            <h2>Vishwas</h2>
            <h2>Codevolution</h2>
            <h2>vue</h2>
        </div>

        <h2 v-show="showElement">Using v-show</h2>
        <h2 v-if="showElement">Using v-if</h2>        
    </div>
</template>

<script>
export default {
    name: 'Conditional',
    data(){
        return{
            num: 5,
            display: true,
            showElement: true
        }
    }
}
</script>

<style>
.conditional-component {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>