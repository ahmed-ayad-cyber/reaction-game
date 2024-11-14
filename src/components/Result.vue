<template>
    <div>
    <P>your reaction time : {{score}} mlsecound</P>
    <p>{{rank}}...</p>
    </div>

</template>

<script>
export default {
    name:"Result",
    props:['score']
    ,data(){
        return {
            rank : null
        }
    },
    mounted (){
        if (this.score< 220  ) {
        this.rank = "you are a ninja"
      }else if (this.score >=220 && this.score <400) {
        this.rank = "you are a normal person"
      }else {
        this.rank = "you are a snail"
      }
    }
}
</script>

<style>

</style>