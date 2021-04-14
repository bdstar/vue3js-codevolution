<template>
  <div>
    <!-- Binding Text -->
    <div>{{greet}} {{name}}</div>
    <div v-text="channel"></div>

    <!-- Binding HTML -->
    <div v-html="html"></div>
    <div v-html="hack"></div>

    <!-- Binding Attributes -->
    <h2 v-bind:id="headingID">Heading</h2>
    <button v-bind:disabled="isDisable">Bind</button>

    <!-- Binding Classes -->
    <h2 class="underline" v-bind:class="status">underline text</h2>
    <h2 v-bind:class="isPromoted && 'promoted'">Promoted Movie</h2>
    <h2 v-bind:class="isSoldout ? 'sold-out' : 'new'">Sold Out Movie?</h2>
    <h2 v-bind:class="['new', 'promoted']">Newly Promoted Movie</h2>
    <h2 v-bind:class="[isPromoted && 'promoted', isSoldout ? 'sold-out' : 'new']">
      Array Conditional Movie
    </h2>
    <h2 v-bind:class="{
      promoted: isPromoted,
      new: !isSoldout,
      'sold-out': isSoldout 
    }">
    Object Conditional Movie
    </h2>

    <!-- Binding Style -->
    <h2 v-bind:style="{ color: hightlightColor, fontSize: headerSize + 'px', padding: '20px'}">Inline Style</h2>  

    <h2 v-bind:style="headerStyleObject">Style Object</h2>  
    <div v-bind:style="[baseStyleObject, SuccessStyleObject]">Success Style</div>
    <div v-bind:style="[baseStyleObject, dangerStyleObject]">Danger Style</div> 

    <!-- v-bind shorthand -->
    <h2 :class="isPromoted && 'promoted'">Promoted Movie</h2> 
    <h2 :id="headingID">Heading</h2>  
    <h2 :style="headerStyleObject">Style Object</h2> 
  </div>
</template>

<script>
export default {
    name: 'Binding',
    data(){
        return{
            greet: 'Hello',
            name: "Batman",
            channel: "Codevolution",
            html: "<b>This is HTML</b>",
            hack: `<a href="#" onclick="alert('You have been hacked!')">Win a Prize!</a>`,
            headingID: 'heading',
            isDisable: true,
            status: 'danger',
            isPromoted: true,
            isSoldout: false,
            hightlightColor: 'orange',
            headerSize: 30,
            headerStyleObject: {
                color: 'orange',
                fontSize: '30px',
                padding: '20px'
            },
            baseStyleObject: {
                fontSize: '30px',
                padding: '10px'
            },
            SuccessStyleObject: {
                color: 'green',
                backgroundColor: 'lightgreen',
                border: '1px solid green',
                padding: '20px'
            },
            dangerStyleObject: {
                color: 'darked',
                backgroundColor: 'red',
                border: '1px solid darked'
            },      
        }
    }
}
</script>

<style>
.underline{
  text-decoration: underline;
}

.promoted{
  font-style: italic;
}
.new{
  color: green;
}
.sold-out{
  color: red;
}
</style>