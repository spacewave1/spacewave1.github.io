<template>
  <div class="framePoint" :style="{right:`${x}px`,top:`${y}px`, color: `${color}`}" @mouseover="toPointer" @mouseout="toCursor" @click="open">
    <div class="point">
    </div>
  </div>
</template>

<script>
export default {
  name: 'FolioNode',
  props: {
    x: Number,
    y: Number,
    color: String,
    id:String
  },
  methods: {
    open(){
      console.log("open")
    },
    toPointer(){
      document.body.style.cursor = "pointer"; 
    },
    toCursor(){
      document.body.style.cursor = "default"; 
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.point{
  position: relative;
}
.point:before{
  content: ' \25CF';
  font-size: 20px;
}
.framePoint {
  position: absolute;
  width: 50px;
  height: 50px;
  transform: translateX(25px);
  z-index: 10;
}
</style>
