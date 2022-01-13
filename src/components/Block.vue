<template>
  <div class="block" v-if="showBlock">
      Click Me
      </div>
</template>

<script>
export default {
props: ['delay'],
data(){
    return{
        showBlock: false
    }
},
mounted(){
    console.log('component mounted')
    setTimeout(()=>{
        this.showBlock = true
        console.log(this.delay)
    }, this.delay)
},
updated(){

}
}
</script>

<style>
.block{
    width: 250px;
    height: 250px;
    border-radius: 4px;
    background: rgb(66, 199, 86);
    text-align: 100px 50px;
    margin: 40px auto;
}
</style>