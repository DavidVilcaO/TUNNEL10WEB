<template>
  <div id="app">
    <Menus/>
    <HelloWorld msg="The Original Tunnel10"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
import Menus from './components/Menus.vue';

export default {
  name: 'app',
  components: {
    HelloWorld,
    Menus,
  },
};
</script>
<style lang="stylus">

body
  margin 0px
  padding 0px

#app
  height 100vh
  // font-family 'Avenir', Helvetica, Arial, sans-serif
  font-family: 'Roboto', sans-serif;
  -webkit-font-smoothing antialiased
  -moz-osx-font-smoothing grayscale
  text-align center
  color #2c3e50
  padding 10px
  // background-color #0E0E0E
  background-image linear-gradient(
      rgba(0, 0, 0, 1),
      rgba(0, 0, 0, 1),
      rgba(0, 0, 0, 0.9)
    ), url('assets/bg1.jpg')
  background-repeat no-repeat
  background-size cover
</style>
