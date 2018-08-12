<template lang="html">
  <div id="page">

    <button @click="addPage">+</button>
  </div>
</template>

<script>

export default {
  data(){
    return{

    }

  },
  methods:{
    addPage(){

    }
  }
}






</script>

<style lang="css" scoped>
  div{
    color:blue;
  }

  #page{
    width:800px;
    height:500px;
    border:1px solid gray;
    /* margin-left: 300px; */
    display: inline-block;
  }
  button{
    font-size: 100pt;
  }
</style>
