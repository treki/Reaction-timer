<template>
    <p>Reaction Time: {{ score }} ms</p>
    <p class="rank">{{rank}}</p>
</template>

<script>
export default {
    props: [ 'score'],
    data(){
        return {
            rank: null
        }
    },
    mounted(){
        if(this.score < 350){
            this.rank = "Ninja Fingers"
        } else if (this.score < 700){
            this.rank = "Rapid Flexes"
        }else {
            this.rank = "Too Slow"
        }
    } 
}
</script>

<style>
    .rank {
        color: rgb(66, 199, 86);
        font-size: 25px;
        font-weight: bold;
    }
</style>