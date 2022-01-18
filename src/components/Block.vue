<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
      Click Me
      </div>
</template>

<script>
export default {
props: ['delay'],
data(){
    return{
        showBlock: false,
        timer: null,
        reactionTime: 0
    }
},
mounted(){
    console.log('component mounted')
    setTimeout(()=>{
        this.showBlock = true
        console.log(this.delay)
        this.startTimer()
    }, this.delay)
},
methods: {
    startTimer(){
        this.timer = setInterval(() =>{
            this.reactionTime += 10
        }, 10)
    },
    stopTimer(){
        clearInterval(this.timer)
        this.$emit('end', this.reactionTime)
    }
}

}
</script>

<style>
.block{
    width: 150px;
    border-radius: 4px;
    background: rgb(66, 199, 86);
    text-align: center;
    padding: 50px 0;
    margin: 40px auto;
}
</style>