

<template >
<div class="game">
<h1>rection timer</h1> 
<button @click="start" :disabled="isPlaying">play</button>
<Block v-if="isPlaying" :delay="delay" @end="endGame"/>
<Result  v-if="showResult" :score="score" />
</div>
<!-- <p>{{score}}</p> -->
</template>
<script >
import Block from './component/Block.vue'
import Result from './component/Result.vue'
export default{
  name:'App',
  components:{Block,Result},
  data(){
    //propety for functions
    return{
      isPlaying:false,
      delay:null,
      score:null,
      showResult:false
    }
  },
  methods:{
    start(){
      // give us amount time beetwen 2s to 7s
      this.delay= 2000+Math.random()*5000;
this.isPlaying=true
 this.showResult=false

    },
    endGame(reactionTime){
this.score = reactionTime
this.isPlaying=false
 this.showResult=true

    }
  }
}
</script>

<style >
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@300&display=swap');
body{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Open Sans', sans-serif;
    background-color: rgb(40, 40, 40);
}
.game{
  
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin: 0 auto;

  color: #f1f0f0;
  height: 100vh;
   text-transform: uppercase;
   letter-spacing: 3px;
   width: 300px;
  
}
button{
  padding: 1rem 3rem;
  border-radius: 10px;
  border: none;
  outline: none;
  background-color:#8b8a8c;
  color: #f0f0f0;
  font-size: 2rem;
}


</style>