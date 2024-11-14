<template>
  <div>
    <h1>the reaction Game test your self</h1>
    <button @click="startPlay" :disabled="isPlaying">play</button>
    <result v-if="Result" :score="score" />
    <Block v-if="isPlaying" :randomTime="randomTime" @scoreTime="showResult" />
  </div>
</template>

<script>
import Block from './components/Block.vue';
import Result from './components/Result.vue';
export default {
  name: 'App',
  components: {Block,Result},
  data(){
    return {
      isPlaying:false,
      randomTime:null,
      score:null,
      Result:false,
    }},
  methods:{
    startPlay(){
      this.isPlaying =true
      this.Result = false
      this.randomTime = 200 + Math.random() *5000
    },
    showResult(theScore){
      this.score =theScore
      this.isPlaying =false
      this.Result=true 
    }
  }
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
