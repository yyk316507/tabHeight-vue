<template>
  <div id="app">
    <div class="collection">
      <a href="#!" class="collection-item"
        v-for="gameName in gameNames"
        @click="selected(gameName)"
        :class="{active:activeName ==gameName}"
      >{{gameName}}</a>

    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      gameNames:['魔兽世界','看电视呢开发','王者荣耀','守望'],
      activeName:''
    }
    
  },
  methods:{
    selected:function(gameName){
      this.activeName = gameName
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
.active { background: red }
</style>
