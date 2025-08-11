<template>
  <h1> Reaction Timer</h1>
  <button @click="start">Start</button>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';

@Options({
  components: {
  
  },
  data(){
    return{
      isPlaying:false,
      delay:null
    }
  }
  ,
  methods:{
    start(){
      this.delay=2000+Math.random() *3000
      this.isPlaying=true
      console.log(this.delay)
    }
  }
})
export default class App extends Vue {}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
</style>
