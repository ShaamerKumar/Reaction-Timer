<template>
  <p>Reaction Time: {{score}} ms</p>
  <h3 class="rank">{{rank}}</h3>
  
</template>

<script>
export default {
    props:['score'],
    data() {
        return{
            rank:null
        }
    },
    mounted(){
        if (this.score < 320){
            this.rank = 'LEGENDARY REFLEXES'
        }
        else if (this.score < 450){
            this.rank = 'Rapid Reflexes'
        }
        else {
            this.rank = 'Wow you are slow...'
        }
    }

}
</script>

<style>

</style>