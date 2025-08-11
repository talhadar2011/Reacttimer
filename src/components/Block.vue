<template>
  <div class="block" v-if="showBlock">
    click me
    {{ delay }}
  </div>
</template>

<script>
export default {
 props:["delay"],
 data(){
    return {
        showBlock:false
    }
 },
 mounted(){
    console.log("Component Mounted")
    setTimeout(()=>{
        this.showBlock=true
    },this.delay)

 },
 updated(){
    console.log("Updated")
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