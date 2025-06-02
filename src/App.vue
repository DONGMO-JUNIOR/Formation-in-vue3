<template>
  <div>
     <!--v-bind Style-->
     <h2 v-bind:style="{
      color:highlight
     }">Inline style</h2>
     <h2 v-bind:style="headerSizeObject">Style object</h2>
    <!--v-bind classes-->
    <h2 class="underline">Underlined text</h2>
    <h2 v-bind:class="status"> status</h2>
    <h2 v-bind:class="isPromoted && 'promoted' "> Promoted Movies</h2>
    <h2 v-bind:class="isSoldout ? 'sold-out' : 'new'">Soldout? movie</h2>
    <h2 v-bind:class="['new', 'promoted']">Newly promoted movie</h2>
    <h2 v-bind:class="[isPromoted && 'promoted', isSoldout ? 'sold-out' : 'new']"> Array conditional movie</h2>
      
    <!--v-bind attribut-->
     <h2 v-bind:id="headingId">Heading</h2>
    <button v-bind:disabled="isDisable">Bind</button>
    <!--v-bind html-->
    <div>{{ greet }} {{ name }}</div>
    <div>{{ channel }}</div>
    <div v-html="channel"></div>
    <h1 v-html="hack"></h1>

    <!--v-bind text-->
    <div>{{ greet }} {{ name }}</div>
    <div v-text="channel"></div>
    <div v-text="name"></div>
  </div> 
</template>

<script>
  export default {
    name: "App",
    data(){
return{
  greet: 'Hello',
  name: 'Batman',
  channel: '<b>codevolution</b>',
  hack: `<a href='#' onclick= "alert('You have been hacked')"> win a prise! </a>`,
  headingId: 'heading',
  isDisable: true,
  status: "danger",
  isPromoted: false,
  isSoldout:false,
  highlight:'orange',
  headerSizeObject: {
    color: 'blue',
    fontSize: '50px',
    padding: '15px'
  }
}
    }
  }
</script>

<style scoped>
.underline{
  text-decoration: underline ;
}
.promoted{
  color: red
}
.sold-out{
  color: blue
}
.new{
  font-style: italic;
}
</style>