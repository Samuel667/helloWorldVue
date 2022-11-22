<template>
   <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  <div class="container">
    <div class="row"></div>
    <div class="col-md-12">
      <post-Create></post-Create>
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import PostCreate from './components/Post-Post.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    PostCreate
  
  }
}
</script>

<style>
</style>
