<template>
<div>
     <div class="row">
       <div class="col-sm-12">
         <div id="textcol">
       <h1>GAME</h1>
       </div>
  </div>
  </div>
  <br>
  <div class="row">
        <div class="col-sm-4">
           <div id="textcol">
           <h1>PLAYER</h1>
           </div>
           <br>
            <img style="width:45%" :src="selectedplayer.image"  alt=""> 
            
    </div>
    
      <div class="col-sm-4">
              <h1>INFINITY WAR</h1>
              <br>
              <button @click="created()" class ="btn btn-danger">START</button>
              <br>
              <br>
              <img src="@/assets/vs.png" alt="Image alt" width ="30%" > 
              <div id="score">
              <h1>Player : {{herohp}}</h1>
              </div>
              {{space}} {{space}} {{space}} 
              <div id="score">
              <h1>Monster : {{monshp}}</h1></div>
             <br>
             <button @click="randomat()" v-bind:disabled = "end" class ="btn btn-dark">ATTACK</button> 
             {{space}} 
             <button @click="ultimate()" v-bind:disabled = "end" class ="btn btn-dark">ULTIMATE</button>
         </div>
      <div class="col-sm-4">
        <div id="textcol">
        <h1>MONSTER</h1>
        </div>
        <br>
  <img style="width:45%"  :src="selectedmonster.image"  alt="">
  <br>
  <br>
      </div>
  </div>
  <div class="row">
    <div class="col-sm-4">
      <div id="score">
  <h1>Player : {{selectedplayer.name}}</h1>
 </div>
    </div>
    <div class="col-sm-4">
 
    </div>
    <div class="col-sm-4">
      <div id="score">
      <h1>Monster : {{selectedmonster.name}}</h1>
</div>
    </div>
  </div>
  <div id="result">
      <div v-if="monshp == 0">      
        Player win
    </div>
    <div v-else-if="herohp  == 0">
        Monster win
    </div>
    </div>
  </div>
</template>

<script>
export default {
name: 'randomstart',
    data: function() {
  return{
    player: [
        {name: "Mark85",herohp: 200 ,image:"https://www.pinclipart.com/picdir/big/169-1695678_iron-man-fly-photo-iron-man-mk-50.png",},
        {name: "Professor Hulk",herohp: 225 ,image: "https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/9fc0b682-d0de-4d16-a100-28776d2a48f7/dd53njb-7ad5d804-c418-42b8-acd0-3b242cda2faf.png?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOiIsImlzcyI6InVybjphcHA6Iiwib2JqIjpbW3sicGF0aCI6IlwvZlwvOWZjMGI2ODItZDBkZS00ZDE2LWExMDAtMjg3NzZkMmE0OGY3XC9kZDUzbmpiLTdhZDVkODA0LWM0MTgtNDJiOC1hY2QwLTNiMjQyY2RhMmZhZi5wbmcifV1dLCJhdWQiOlsidXJuOnNlcnZpY2U6ZmlsZS5kb3dubG9hZCJdfQ.PSJU5MDFR_tnRph1fl6KFTphN2ekzUp_1X6YcqzNJ6s",},
        {name: "Thor",herohp: 250 ,image: "https://i.imgur.com/XSqKLDq.png",},
      ],
      Monster: [
        {name: "Thanos",monshp: 250 ,image:"https://i.pinimg.com/originals/44/c8/81/44c881c6e770d1294ea91ae0049fcd22.png",},
        {name: "Nemesis",monshp: 200 ,image: "https://vignette.wikia.nocookie.net/villains/images/3/3a/B8F52267-E5DA-406C-A43B-C21F752D2D76.png/revision/latest/scale-to-width-down/281?cb=20200321004316",},
        {name: "Eternity",monshp: 300 ,image: "https://i.imgur.com/tkU0u01.png",},
      ],
      selectedmonster: {name:"",image:null,},
      selectedplayer : {name:"",image:null,},
      heropow: "",
      monspow: "",
      monshp:null,
      herohp:null,
      term: false,
      end : false,
      space :"",
    
    
}
    },
    methods : {
  randomat: function(){
    this.heropow = Math.floor(Math.random() * 8 + 2);
    this.monshp = this.monshp - this.heropow;
    this.monspow = Math.floor(Math.random() * 5 + 5);
    this.herohp = this.herohp - this.monspow;
    if(this.herohp<=0){
        this.herohp = 0
        this.end = true
      }else if(this.monshp<=0){
        this.monshp = 0
        this.end = true
      }
  },
  ultimate: function(){
    this.heropow = Math.floor(Math.random() * 14 + 1);
    this.monshp = this.monshp - this.heropow;
    this.monspow = Math.floor(Math.random() * 13 + 2);
    this.herohp = this.herohp - this.monspow;
    if(this.herohp<=0){
        this.herohp = 0
        this.end = true
      }else if(this.monshp<=0){
        this.monshp = 0
        this.end = true
      }
  },
 randommonster (items) {
      return items[Math.floor(Math.random()*items.length)];
    },
  randomplayer (items) {
      return items[Math.floor(Math.random()*items.length)];
    },
     created : function() {
    this.selectedmonster = this.randommonster(this.Monster)
    this.selectedplayer = this.randomplayer(this.player)
    this.herohp = this.selectedplayer.herohp
    this.monshp = this.selectedmonster.monshp
    this.end = (false)
  },
}
}
</script>

<style>
#result{
  height : 50px;
  font-size : 200%;
  color :aliceblue;
}
#textcol{
color: rebeccapurple;
}
#score{
  color: red;
}
</style>