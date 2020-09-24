<template>
  <div id="app" @mousemove="update">
    <li v-for="item in items" :key="item.message">
      <ul>
        <FolioNode :x="compX(item)" :y="Math.sin(item+index)*100 + y" :color="'#0000AA'"/>
        <Link :x1="compX(item)" :y1="Math.sin(item+index)*100 + y" :x2="compX(item+1)" :y2="Math.sin(item+index+1)*100 + y" :color="'#0000AA'" :id="item.toString()"/>
      </ul>
    </li>
    <li v-for="item in items" :key="item.message">
      <ul>
        <FolioNode
        :x="compX(item)"
        :y="Math.sin(item+index+3)*200 + y"
        :color="'#AA0000'"
        />
        <Link :x1="compX(item)" :y1="Math.sin(item+index+3)*200 + y" :x2="compX(item+1)" :y2="Math.sin(item+index+3+1)*200 + y" :color="'#AA0000'" :id="item.toString()"/>
      </ul>
    </li>
    <li v-for="item in items" :key="item.message">
      <ul>
        <FolioNode
        :x="compX(item)"
        :y="Math.sin(item+index+30)*170 + y"
        :color="'#00AA00'"
        :id="item.toString()"
        />
        <Link :x1="compX(item)" :y1="Math.sin(item+index+30)*170 + y" :x2="compX(item+1)" :y2="Math.sin(item+index+30+1)*170 + y" :color="'#00AA00'" :id="item.toString()"/>
      </ul>
    </li>
    <div id="background" @mousemove="update"></div>
  </div>
</template>

<script>
import FolioNode from './components/FolioNode';
import Link from './components/Link';

export default {
  name: 'App',

  components: {
    FolioNode,
    Link
  }, 
  methods: {
    update: function() {
      this.index += 0.03
    },
    compX(item){
      return item * this.x/this.items.length
    }
  },
  data: () => ({
    x: window.innerWidth,
    y: window.innerHeight/2,
    items:[1,2,3,4,5,6,7,8,9,10,11,12],
    index:0
  })
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#background {
  position: fixed;
    width: 100%;
    height: 100%;
    left: 0;
    top: 0;
    background: rgba(0,0,0,1);
    z-index: -10;
}
</style>
