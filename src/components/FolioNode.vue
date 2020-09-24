<template>
  <div :style="{right:`${x}px`,top:`${y}px`, color: `${color}`}" class="point">
  </div>
</template>

<script>
export default {
  name: 'FolioNode',
  props: {
    x: Number,
    y: Number,
    color: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.point{
  position: absolute;
}
.point:before{
  content: ' \25CF';
  font-size: 20px;
}
</style>
