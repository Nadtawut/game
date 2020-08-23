<template>
<div>
  <br>

</div>
</template>

<script>
export default {
name:'RandomDam',
data: function() {
  
},
props:{
    label:String, 
  },
  methods : {
  randomDamage: function(min, max) {          
     return Math.HP(Math.floor(Math.random() * max) + 1,min);   

     },
  }, 
}


</script>

<style>

</style>