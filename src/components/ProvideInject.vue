<template>
  <div>
      <!---
                                    App
                                     |
        ---------------------------------------------------------------------
        |                            |                                      |
        A                            B                                      C
                                     |                                      |
                                     D                                      E
                                                                            |
                                                                            F  
      -->
      <h2>------------ Provide Inject -----------</h2>
      <h3>App Component username {{piname}}</h3>
      <ComponentC/>
  </div>
</template>

<script>
import ComponentC from "../provideinject/ComponentC.vue";
export default {
    name: 'ProvideInject',
    data(){
        return{
          piname: 'Vishwas'
        }
    },
    components: {
      ComponentC,
    },
    provide() {
      return{
        username: this.piname,        
      }

    }
}
</script>

<style>

</style>