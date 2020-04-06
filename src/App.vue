<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <Header></Header>
    <div>
      <Input></Input>
      <Content></Content>
    </div>   
  </div>
</template>

<script>
import Header from './components/Header';
import Input from './components/Input';
import Content from './components/Content';

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
