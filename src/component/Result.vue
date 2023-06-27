<template >
<div class="score">

    <p>{{score}} {{rank}}</p>  

</div>

</template>

<script>
import { onMounted } from 'vue'
export default {
 props: ["score"],
 data(){
    return{
        rank:null
    }
 },
mounted(){
if(this.score < 300){
    this.rank = "Ninga finger"
}else if(this.score < 400){
     this.rank = "hmmm okey will done :("
}else{
     this.rank = "snail pice... :|"
}
 }
}
</script>

<style>

.score {
  background-color: rgb(8, 173, 104);
  width:90%;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
  color: aliceblue;
  border: 2px solid #fff;
  border-radius: 50%;
  font-size: 1rem;
   text-transform: uppercase;
}
</style>