<template>
    <div>
        <h2>------------ Method --------------</h2>
        <h2>{{ 1 + 2 + 3 }}</h2>
        <h2>Add: {{ add(2,5,7) }}</h2>
        <h2>Multiply: {{ multiply(baseValue) }}</h2>
    </div>
</template>

<script>
export default {
  name: 'Methods',
  data() {
    return{
        baseMultiplier: 5,
        baseValue: 2
    }
  },
  methods: {
      add(a, b, c){
          return (a + b + c);
      },
      multiply(num){
          return num * this.baseMultiplier
      }
  }
}
</script>

<style>

</style>