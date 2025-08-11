<template>
  <div>
    <h1> Reaction Timer</h1>
    <button @click="start" :disabled="isPlaying">Start</button>
    <Block v-if="isPlaying" :delay="delay"/>
  </div>
  
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import Block from './components/Block.vue';
@Options({
  components: {
  Block
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
    }
  }
})
export default class App extends Vue {start:any ;isPlaying: any;
  delay: any;
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
</style>
