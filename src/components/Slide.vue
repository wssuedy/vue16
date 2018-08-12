<template>


  <div id="slide">
    <div class="leftBar">
      <form v-on:submit.prevent="addNewTodo">
        <label for="createPage">创建新的页面 </label>
        <!-- <br>
        <input
          v-model="newPageTitle"
          id="createPage"
          placeholder="请输入新的页面标题"
        >
        <br> -->
        <button>创建</button>
      </form>
    </div>

  <!-- <ul> -->
  <div class="pagechange">

    <button v-show="currPageId>1"  v-on:click="currPageId -= 1">上一页</button>

    <button v-show="currPageId<nextPageId-1" v-on:click="currPageId += 1">下一页</button>
  </div>


    <Page
      v-for="(page, index) in pages"
      v-bind:key="page.id"
      v-bind:pagenum="page.id"
      v-bind:index=index
      v-bind:title=title
      v-bind:currPageId=currPageId
      v-bind:nextPageId=nextPageId
      v-on:remove="pages.splice(index, 1)"
      v-on:nextPage="currPageId += 1"
      v-on:prePage="currPageId -= 1"
    ></Page>
  <!-- </ul> -->

  <div>

  </div>

</div>

</template>

<script>
import Page from './Page.vue';

export default {

  components: {
    Page
  },
  data(){
    return{
      currPageId: 1,
      newPageTitle: '',
      pages: [
          {
            id: 1,
            title: '',
          },
          {
            id: 2,
            title: '',
          },
          {
            id: 3,
            title: ''
          }
        ],
        nextPageId: 4
    }
  },
  methods: {
   addNewTodo: function () {
     this.currPageId=this.nextPageId;
     this.pages.push({
       id: this.nextPageId++,
       title: this.newPageTitle
     })
     this.newPageTitle = '';

   }
 }


}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
#slide{
  /* width:250px; */
  /* height: 500px; */
  border:1px solid gray;
  /* margin-left: 20px; */
}

.leftBar{
  float:left;
  position: fixed;
  top:100px;
  left:30px;
}

.pagechange{

  background-color: gray;

}

</style>
