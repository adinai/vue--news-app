<template>
  <div id="app">
    <h1 class=" container text-center mb-5">My Component based Structure</h1>
    <div class="row">
      <div class="col-md-7 col-12">
        <news-holder v-on:read="newsRead" date="yesterday"></news-holder>
      </div>
      <div class="col-md-2 d-sm-none d-md-block">
        <link-holder></link-holder>
        <adds-holder></adds-holder>
      </div>

      </div>
    </div>
</template>

<script>
export default {
  name: 'app',
  methods:{
    newsRead(num){
      alert('You read news! Number is: ' + num)
    }
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
}
</style>
