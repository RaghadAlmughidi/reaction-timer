<template>
  <div class="block" v-if="showBlock" @click="stopTimer">click me</div>
</template>

<script>
export default {
  props: ["delay"],
  data() {
    return {
      showBlock: false,
      timer:null,
      reactionTime:0
    };
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer()
    }, this.delay);
  },
  methods:{
    startTimer(){
     this.timer= setInterval(() => {
        this.reactionTime +=10
     }, (10));
    },
    stopTimer(){
clearInterval(this.timer)
this.$emit('end',this.reactionTime)
    }
  }
};
</script>

<style>
.block {
  background-color: rgb(8, 173, 173);
  width:250px;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
  color: aliceblue;
  border: 2px solid #fff;
  border-radius: 50%;
  font-size: 2rem;
   text-transform: uppercase;
}
</style>
