<template>
  <div id="app">
    <intro></intro>
    <navbar v-on:sourceChanged="sourceChanged" class="navbar"></navbar>
    <newslist v-bind:source="source"></newslist>
    <appFooter class="appfooter"></appFooter>
  </div>
</template>

<script>
import navbar from './components/navbar'
import newslist from './components/newslist'
import appFooter from './components/appFooter'
import intro from './components/intro'

export default {
  name: 'app',
  components: { 
   navbar,
   newslist,
   appFooter,
   intro
  },
  data (){
     return{
      source:''
    }
  },
  methods:{
    sourceChanged (source){
      this.source = source
    }
  }
}
</script>

<style>
.navbar{
  margin-bottom: 20px;
}
.appfooter{
  margin-top:10px;
}
</style>
