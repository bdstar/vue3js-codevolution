<template>
    <div>
        <h2>---------- Conditional List Rendering -----------</h2>
        <div v-for="namelist in namelists" :key="namelist">
            <h2 v-if="namelist === 'Bruce'">{{namelist}}</h2> 
        </div>   
    </div>
</template>

<script>
export default {
    name: 'ConditionalListRendering',
    data(){
        return{
            namelists: ['Bruce', 'Clark', 'Diana']
        }
    }
}
</script>

<style>

</style>