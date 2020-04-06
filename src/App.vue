<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <Header></Header>
    <Input></Input>
    <Content></Content> 
  </div>
</template>

<script>
import Header from './components/Header';
import Input from './components/Input';
import Content from './components/Content';

import bus from './js/bus.js';

export default {
  name: 'App',
  components: {
    Header,
    Input,
    Content
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  /*text-align: center;*/
}
</style>
