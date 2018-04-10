<template>
  <div id="app">
    <div class="collection">
      <a href="#!" class="collection-item"
        v-for="gameName in gameNames"
        @click="selected(gameName)"
        :class="{active:activeName ==gameName}"
      >{{gameName}}</a>

    </div>
    <div id="myChart" 
      :style="{width:'300px',height:'300px'}"
    ></div>
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
  mounted(){
    this.drawLine();
  },
  methods:{
    selected:function(gameName){
      this.activeName = gameName
    },
    //基于准备好的dom，初始化echarts实例
    drawLine:function(){
      let myChart = this.$echarts.init(document.getElementById('myChart'))
      //绘制图表
      myChart.setOption({
        title:{text:'在vue中使用echarts'},
        tooltip:{},
        xAxis:{
          data:["衬衫","羊毛衫","雪纺衫","裤子","高跟鞋","袜子"]
        },
        yAxis:{},
        series:[{
          name:'销量',
          type:'bar',
          data:[5,20,36,10,10,20]
        }]
      })
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
