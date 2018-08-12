<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <Slide></Slide>

    <!-- <div v-for="page in pages" :key="page.id">

      <Page v-bind:pagenum="page.id"></Page>
      </div> -->

    <!-- <Page v-bind:pagenum="2"></Page>

    <Page v-bind:pagenum="3"></Page> -->


  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
import Page from './components/Page.vue';
import AddPage from './components/AddPage.vue';
import Slide from './components/Slide.vue';

export default {
  name: 'app',
  num:[1,2,3],


  components: {
    HelloWorld,AddPage,Slide,Page
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  width:100%;
  border:1px solid red;
}
Page{
  /* display: inline; */
}
AddPage{
  display: inline;
}
</style>
