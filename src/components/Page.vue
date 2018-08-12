<template lang="html">
  <div id="page" v-show="currPageId==index+1">
    <div class="title">
      <!-- <p>{{title}}</p> -->
      <!-- <p>{{ pageTitle }}</p> -->
      <input v-model="pageTitle" type="textarea" maxlength="16" minlength="6" style="width:600px;height:20px;" placeholder="编辑标题"/>
    </div>

    <!-- {{ name }} -->
    <hr>
    <div class="content">
      <!-- {{ pageContent}} -->

      <textarea v-model="pageContent" rows="6" cols="80" name="" value="编辑内容" ></textarea>
      <!-- <textarea name="name" rows="6" cols="80">{{ pageContent}}</textarea> -->
    </div>
    <div class="picture">
      <textarea v-model="pageDes" rows="19" cols="46" name="" value="编码描述" ></textarea>
    </div>


    <button id="prePage" v-on:click="$emit('prePage')" v-bind:disabled="currPageId==1">上一页</button>
    <!-- age:{{ age }} -->
    <!-- page:{{ pagenum }} -->
    page:{{index+1}}
    <!-- currPageId:{{currPageId}} -->
    <button id="remove" v-on:click="$emit('remove')">Remove</button>



    <button id="nextPage" v-on:click="$emit('nextPage')" v-bind:disabled="currPageId==(nextPageId-1)">下一页</button>

    <!-- <button @click="add">add</button> -->
  </div>
</template>
<script>

export default {
  props: {
    pagenum: String,
    index:Number,
    currPageId:Number,
    nextPageId:Number,
    title:String
  },
  data(){
    return{
      name:"wss",
      age:18,
      page:1,
      pageTitle:"请输入标题",
      pageContent:"请输入内容",
      pageDes:"请详细描述"
    }

  },
  methods:{
    add(){
      ++this.age;
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
    /* height:500px; */
    border:1px solid gray;
    /* margin-left: 300px; */
    /* display: inline-block; */
    margin: 10px auto;

  }
  .content{
    width:500px;
    height:100px;
    border:1px solid gray;
    margin: auto;
  }

  .picture{
    width:300px;
    height:300px;
    border:1px solid gray;
    margin: 5px auto;
  }

  input,textarea{
    border:0;
    margin-top: 5px;
  }

 #prePage{
   position: relative;
   left:-200px;
 }

 #nextPage{
   position: relative;
   left:200px;
 }
</style>
