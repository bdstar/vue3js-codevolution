<template>
  <div>
      <h2>Component E</h2>
      <ComponentF/>
  </div>
</template>

<script>
import ComponentF from "./ComponentF.vue";

export default {
    name: 'ComponentE',
    data(){
        return{

        }
    },
    components: {
      ComponentF,
  }

}
</script>

<style>

</style>