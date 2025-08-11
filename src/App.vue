<template>
  <div>
    <h1> Reaction Timer</h1>
    <button @click="start" :disabled="isPlaying">Start</button>
    <Block v-if="isPlaying" :delay="delay" @result="getResult"/>
    <Results v-if="showResult" :score="score"/>
  </div>
  
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import Block from './components/Block.vue';
import Results from './components/Results.vue';
@Options({
  components: {
  Block,
  Results
  },
  data(){
    return{
      isPlaying:false,
      delay:null,
      score:null,
      showResult:false
    }
  }
  ,
  methods:{
    start(){
      this.delay=2000+Math.random() *3000
      this.isPlaying=true
      this.showResult=false
    },
    getResult(ReactionTime: any){
      this.score=ReactionTime;
      console.log(this.score)
      this.isPlaying=false
      this.showResult=true
    }
  }
})
export default class App extends Vue {start:any ;isPlaying: any;
  delay: any;
  getResult: any;
  score:any
}
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
button{
  background-color: #444;
  color:white;
  font-size: large;
  border-radius: 4px;
  padding: 10px 20px;
  margin: 10px;
  cursor: pointer;
  letter-spacing: 1px;
}
button[disabled]{
opacity: 0.5;
cursor: not-allowed;
}
</style>
