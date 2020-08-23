<template>
<div>
  <br>

       </div> 
</template>

<script>
export default {
    name: 'Csbotton',
    data: function() {
  return{
    player: [
        {name: "mark85", hp:"1000", image:"https://www.pinclipart.com/picdir/big/169-1695678_iron-man-fly-photo-iron-man-mk-50.png",},
        {name: "Anakin Skywalker", hp:"500",image: "https://www.freepngimg.com/thumb/minecraft/20-2-minecraft-3d-character-png.png",},
        {name: "Doraemon", hp:"550",image: "https://www.freepngimg.com/thumb/frozen/28780-4-frozen-olaf-transparent-image.png",},
      ],
      Monster: [
        {name: "Thanos",hp:"1200", image:"http://www.pngmart.com/files/9/Marvel-Thanos-PNG-Free-Download.png",},
        {name: "Anakin Skywalker",hp:"500",image: "https://www.freepngimg.com/thumb/minecraft/20-2-minecraft-3d-character-png.png",},
        {name: "Doraemon",hp:"550",image: "https://www.freepngimg.com/thumb/frozen/28780-4-frozen-olaf-transparent-image.png",},
      ],
    
    counter: 0,
    fsize:60,
    }
  },
  props:{
    label:String,
    
  },
  methods : {
  upFunction: function(){
    this.counter += 1
    this.fsize += 10
  this.$emit('cc',this.fsize)

    console.log(this.fsize);
    console.log(this.counter);
  },
    downFunction: function(){
    this.counter -= 1
    this.fsize -= 10

    console.log(this.fsize);
    console.log(this.counter);
    },
    
  },
}
</script>

<style>

</style>