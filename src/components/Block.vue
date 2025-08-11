<template>
  <div class="block" v-if="showBlock" @click="stoptimer">
    click me
  </div>
</template>

<script>
export default {
 props:["delay"],
 data(){
    return {
        showBlock:false,
        Timer:null,
        ReactionTime:0
    }
 },
 mounted(){
    setTimeout(()=>{
        this.showBlock=true
        this.startTimer()
    },this.delay)
   

 },
 methods:{
     startTimer(){
        this.Timer=setInterval(()=>{
            this.ReactionTime+=10
        },10)
    },
    stoptimer(){
        clearInterval(this.Timer)
        this.$emit('result',this.ReactionTime)

        this.showBlock=false
    }
 }

}
</script>

<style>
    .block{
        width: 400px;
        border-radius: 20px;
        background-color: black;
        color: #fff;
        padding: 100px 0;
        text-align: center;
        margin:40px auto;
    }
</style>