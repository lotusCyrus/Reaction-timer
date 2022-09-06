<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <h1>Reaction tiner</h1>
  <button @click="start" :disabled="isplaying" >Start</button>
  <Block v-if="isplaying" :delay="delay"/>
</template>

<script>
import Block from "./components/Block.vue"
export default {
  name: 'App',
  components:{Block},
  data(){
      return{
     isplaying:false,
     delay:null
      }
  },
  methods:{
      start()
      {
         this.isplaying=true
  
      }
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
