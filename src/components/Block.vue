<template>
  <div  class="block" v-if="showBlock" @click="stopTimer">
    click me
  </div>
</template>

<script>
export default {
    name:"block",
    components:{},
    props: ['randomTime'],
    data(){
        return{
            showBlock:false,
            time:null,
            scoreTime:0,
        }
    },
    mounted(){
       setTimeout(()=>{
            this.showBlock=true
            this.startTimer()
        },this.randomTime)
    },
    methods:{
        startTimer(){
            this.time=setInterval(() => {
                this.scoreTime += 10
            }, 10);
        },
        stopTimer(){
            clearInterval(this.time)
            this.$emit('scoreTime',this.scoreTime)
        },
    },
}
</script>

<style>
.block {
    width: 400px;
    border-radius: 20px;
    background-color: #0faf87;
    color: white;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
}
</style>