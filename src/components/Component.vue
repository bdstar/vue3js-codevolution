<template>
  <div>
      <h2>Hello, 
        <span v-bind="$attrs">{{ name }} </span> also know as 
        <span>{{ heroName }}</span>  People Likes 
        <span>{{likes}}</span>  that is 
        <span>{{isPublished ? 'Publised' : 'Not Published'}}</span>  
      </h2>
  </div>
</template>

<script>
export default {
    name: 'Components',
    props: {
        name: {
            type: String,
            required: true,
            default: 'No name'
        },
        heroName:{
            type: String,
            default: 'No Hero' 
        },
        likes: {
            type: Number,
            default: 0
        },
        isPublished: {
            type: Boolean,
            default: false
        }
    },
    inheritAttrs: false,
}
</script>

<style>

</style>