<template>
  <div>
    <!-- First Component -->
    <HelloWorld msg="Welcome to VUE.js App"></HelloWorld>

    <!-- Conditional Rendering -->    
    <Binding></Binding>

    <!-- Conditional Rendering -->         
    <Conditional></Conditional>

    <!-- List Rendering -->         
    <ListRendering></ListRendering>

    <!-- Conditional List Rendering --> 
    <ConditionalListRendering></ConditionalListRendering> 

    <!-- Method -->
    <Methods></Methods>

    <!-- Event Handling -->
    <EventHandling></EventHandling> 

    <!-- Form Handling -->
    <FormHandling></FormHandling> 

    <!-- Computed Properties -->  
    <ComputedProperties></ComputedProperties>

    <!-- Watchers --> 
    <Watchers></Watchers>

    <!-- Component -->
    <h2>----------- Component -------------</h2>
    <Components id="super-hero" name="Bruce" heroName="Batman" :likes=50 :isPublished="true" />
    <Components name="Bruce" hero-name="Batman" />    
    <Components name="Clark" heroName="Superman" />
    <Components name="Diana" heroName="Wonder Woman" />  
    <Components :name="name" :heroName="channel" />   

    <!--- ProvideInject -->
    <ProvideInject></ProvideInject>  

    <!--- Component Events -->
    <ComponentEvents></ComponentEvents>   

  </div>
</template>

<script>
import Conditional from "./components/Conditional.vue";
import Binding from "./components/Binding.vue";
import HelloWorld from "./components/HelloWorld.vue";
import ListRendering from "./components/ListRendering.vue";
import ConditionalListRendering from "./components/ConditionalListRendering.vue";
import Methods from "./components/Methods.vue";
import EventHandling from "./components/EventHandling.vue";
import FormHandling from "./components/FormHandling.vue";
import ComputedProperties from "./components/ComputedProperties.vue";
import Watchers from "./components/Watchers.vue";
import Components from "./components/Component.vue";
import ProvideInject from "./components/ProvideInject.vue";
import ComponentEvents from "./components/ComponentEvents.vue";

export default {
  name: 'App',
  data() {
    return{
      //For Components Tag
      name: 'Mamun',
      channel: 'TechNTuts'
    }
  },
  components: {
    Conditional,
    Binding,
    HelloWorld,
    ListRendering,
    ConditionalListRendering,
    Methods,
    EventHandling,
    FormHandling,
    ComputedProperties,
    Watchers,
    Components,
    ProvideInject,
    ComponentEvents
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
