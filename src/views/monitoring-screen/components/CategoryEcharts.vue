<template>
  <div class="category-echarts" ref="categoryEcharts"></div>
</template>

<script>
export default {
  name: 'CategoryEcharts',
  data() {
    return {
      echarts: null,
    }
  },
  mounted() {
    this.echarts = echarts.init(this.$refs.categoryEcharts)
    const option = {
      dataset: {
        source: [
          ['Mon', 120],
          ['Tue', 200],
          ['Wed', 150],
          ['Thu', 80],
          ['Fri', 70],
          ['Sat', 110],
          ['Sun', 130],
        ],
      },
      xAxis: {
        type: 'category',
      },
      yAxis: {
        type: 'value',
      },
      series: [
        {
          type: 'line',
          smooth: true,
        },
      ],
    }
    this.echarts.setOption(option)
  },
  destroyed() {
    this.echarts.dispose()
  },
}
</script>

<style>
.category-echarts {
  width: 300px;
  height: 300px;
  background-color: #0d1426;
}
</style>