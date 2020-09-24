<template>
  <div id="app" @mouseover="update">
    <li v-for="item in items" :key="item.message">
      <ul>
        <FolioNode
        :x="item * x/items.length"
        :y="Math.sin(item+index)*100 + y"
        :color="'#0000AA'"
        />
      </ul>
    </li>
    <li v-for="item in items" :key="item.message">
      <ul>
        <FolioNode
        :x="item * x/items.length"
        :y="Math.sin(item+index+3)*200 + y"
        :color="'#AA0000'"
        />
      </ul>
    </li>
    <li v-for="item in items" :key="item.message">
      <ul>
        <FolioNode
        :x="item * x/items.length"
        :y="Math.sin(item+index+30)*170 + y"
        :color="'#00AA00'"
        />
      </ul>
    </li>
  </div>
</template>

<script>
import FolioNode from './components/FolioNode';

export default {
  name: 'App',

  components: {
    FolioNode,
  }, 
  methods: {
    update: function() {
      this.index += 1
      console.log("test")
    }
  },

  data: () => ({
    x: window.innerWidth,
    y: window.innerHeight/2,
    items:[1,2,3,4,5,6,7,8,9,10,11],
    index:0
  }),
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
</style>
