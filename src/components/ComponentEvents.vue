<template>
    <div>
        <h2>------------ ComponentEvents ---------------</h2>
        <button @click="showPopup = true">Show Popup</button>
        <Popup v-show="showPopup" @close="closePopup"/>
    </div>
</template>

<script>
import Popup from "../componentevents/Popup.vue";
export default {
    name: 'ComponentEvents',
    data(){
        return{
            showPopup: false,
        }
    },
    components: {
      Popup,
    },
    methods: {
        closePopup(name){
            this.showPopup = false
            console.log('Component Event: name=', name)
        }
    }
}
</script>

<style>

</style>