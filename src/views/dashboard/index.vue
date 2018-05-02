<template>
<div class="dashboard-container">
  <el-row>
    <el-col :span="24">
      <div id="chartColumn" style="width:100%; height:600px;"></div>
    </el-col>
  </el-row>

</div>
</template>

<script>
import echarts from 'echarts'

export default {
  name: 'dashboard',
  data() {
    return {
      chartOption: {
        title: {
          text: 'ECharts 入门示例'
        },
        tooltip: {},
        xAxis: {
          data: ['衬衫', '羊毛衫', '雪纺衫', '裤子', '高跟鞋', '袜子']
        },
        yAxis: {},
        series: [{
          name: '销量',
          type: 'bar',
          data: [5, 20, 36, 10, 10, 20]
        }]
      }
    }
  },
  mounted: function() {

    this.chartColumn = echarts.init(document.getElementById('chartColumn'));
    this.chartColumn.setOption(this.chartOption);

  },
  computed: {}
}
</script>

<style rel="stylesheet/scss" lang="scss" scoped>
.dashboard {
    &-container {
        margin: 30px;
    }
    &-text {
        font-size: 30px;
        line-height: 46px;
    }
}
</style>
