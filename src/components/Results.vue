<template>
    <div class="results" >
      <h3> Your Reaction time is {{ score }}</h3>
      <h5>{{rank}}!!</h5>
    </div>
</template>
<script>
export default
{
    props:['score'],
    data(){
        return{
            rank:null
        }
    },
mounted(){
   if(this.score<250)
   {
      this.rank="God speed"
   }
   else if(this.score < 400 && this.score >250)
   {
      this.rank="super speed"
      
   }
   else if(this.score <550 && this.score> 400)
   {
      this.rank="Youre fast"
   }
  else
   {
      this.rank="snail paced" 
   }
}
}
</script>
<style>
    h5{
        color: green;
    }
</style>
