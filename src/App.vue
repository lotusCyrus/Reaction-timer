<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <h1>Reaction tiner</h1>
  <button @click="start" :disabled="isplaying" >Start</button>
  <Block v-if="isplaying" :delay="delay" @end="endGame"/>
  <h3 v-if="result">Raction Time is {{score}} ms!!</h3>
</template>

<script>
import Block from "./components/Block.vue"
export default {
  name: 'App',
  components:{Block},
  data(){
      return{
     isplaying:false,
     delay:null,
     score:null,
     result:false
      }
  },
  methods:{
      start()
      {
         this.isplaying=true
         this.delay=2000 + Math.random() * 5000
  
      },
      endGame(reactionTime){
          this.score=reactionTime
          this.isplaying=false
          this.result=true
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
