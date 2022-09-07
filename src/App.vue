<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <h1>Reaction timer</h1>
  <button @click="start" :disabled="isplaying" >Start</button>
  <Block v-if="isplaying" :delay="delay" @end="endGame"/>
  <Results v-if="result" :score="score"/>
  
</template>

<script>
import Block from "./components/Block.vue"
import Results from "./components/Results.vue"
export default {
  name: 'App',
  components:{Block, Results},
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
button{
    background:#0faf87;
    border:2px solid #0faf87;
    border-radius: 5px;
    color:white;
    padding: 10px
}
button[disabled]
{
    opacity: 0.2;
    cusor:not allowed;
}

</style>
