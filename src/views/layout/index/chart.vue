<!-- //单独导航组件 -->
<template>
    <div class="charts">
        <div ref="chart" style="width: 400px;height:200px;float: left;margin: 10px;"></div>
    </div>
    <!-- 类型 背景颜色 数据不同 -->
</template>

<script>
export default{
  data(){
    return{
        
    }
  },
  props:['type'],
  mounted(){
    this.init();
  },
  methods:{
    init(){
        // 基于准备好的dom，初始化echarts实例
      var myChart = this.$echarts.init(this.$refs.chart);

      // 指定图表的配置项和数据
      var option = {
        title: {
          text: '数据显示'
        },
        tooltip: {},
        legend: {
          data: ['销量']
        },
        xAxis: {
          data: ['衬衫', '羊毛衫', '雪纺衫', '裤子', '高跟鞋', '袜子']
        },
        yAxis: {},
        series: [
          {
            name: '销量',
            type: this.type,
            data: [5, 20, 36, 10, 10, 20]
          }
        ]
      };
      // 使用刚指定的配置项和数据显示图表。
      myChart.setOption(option);
    }
  }
}
</script>

<style>

</style>