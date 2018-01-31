<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div id="E-Chart" :style="{width: '600px', height: '600px'}"></div>
  </div>
</template>

<script>
var echarts = require("echarts");
export default {
  name: "HelloWorld",
  data() {
    return {
      msg: "Welcome to Your Vue.js App"
    };
  },
  methods: {
    drawEcharts() {
      // let myChart = this.$echarts.init(document.getElementById("E-Chart"));
      // 基于准备好的dom，初始化echarts实例
      var myChart = echarts.init(document.getElementById("E-Chart"));
      // 绘制图表
      myChart.setOption({
        title: {
          text: "ECharts 入门示例"
        },
        tooltip: {},
        xAxis: {
          data: ["衬衫", "羊毛衫", "雪纺衫", "裤子", "高跟鞋", "袜子"]
        },
        yAxis: {},
        series: [
          {
            name: "销量",
            type: "bar",
            data: [5, 20, 36, 10, 10, 20]
          }
        ]
      });
    }
  },
  mounted() {
    this.drawEcharts();
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
