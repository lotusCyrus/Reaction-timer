<template>
    
    <div @click="stopTimer" class="block" v-if="showblock">
        click me
    </div>
    
</template>
<script>
  export default{
      props:['delay'],
      data(){
          return{
          showblock:false,
          timer:null,
          reactionTime:0
          }
      },
mounted()
  {
    console.log("components mounted")
    setTimeout(()=>{
        this.showblock=true
        this.startTimer()
      
    }, this.delay)
  },

updated()
{
    console.log("component updated")
},
ummounted(){
    console.log("unmounted")
},

methods:{
    startTimer(){
        this.timer=setInterval(()=>{
        this.reactionTime +=10
      
        },10)
    },
    stopTimer(){
        clearInterval(this.timer)
        console.log("reaction time is " + this.reactionTime)
        this.$emit('end', this.reactionTime)
    }
}
  }  
  
</script>
<style>
   .block{
       width:200px;
       border-radius:20px;
       background: #0faf87;
       color:white;
       text-align: center;
       padding:100px 0;
       margin:40px auto;
   } 
    
</style>