<template>
  <div id="app">
        <randomstart/>  
      <CsBotton/>
        <RandomDam/> 
  </div>
</template>
<script>


import randomstart from './components/ramdomstart'
export default {
  name: 'App',
  components: {
 randomstart,
  },

  data :function(){
    return{
    
    }
  },
  methods: {
    
    sum(counterValue) {
      this.total += counterValue
    },
  },
}
</script>

<style>
#app {
  background-image: cover;
  background-image: url("https://i.pinimg.com/originals/a6/c2/ea/a6c2ea51ac1f3d947be8c1a39a3f3449.jpg");
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  text:center;
}
</style>
