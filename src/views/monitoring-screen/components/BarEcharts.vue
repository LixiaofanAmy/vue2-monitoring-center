<template>
  <div class="bar-echarts" ref="barEcharts"></div>
</template>

<script>
export default {
  name: 'BarEcharts',
  data() {
    return {
      echarts: null,
    }
  },
  mounted() {
    this.echarts = echarts.init(this.$refs.barEcharts)
    const option = {
      legend: {
        orient: 'horizontal',
        left: 'center',
        top: 10,
        textStyle: {
          color: '#ccc',
        },
      },
      dataset: {
        source: [
          ['product', '2015', '2016', '2017'],
          ['Matcha Latte', 43.3, 85.8, 93.7],
          ['Milk Tea', 83.1, 73.4, 55.1],
          ['Cheese Cocoa', 86.4, 65.2, 82.5],
          ['Walnut Brownie', 72.4, 53.9, 39.1],
        ],
      },
      xAxis: { type: 'category' },
      yAxis: {},
      series: [
        {
          type: 'bar',
          stack: 'x',
        },
        {
          type: 'bar',
          stack: 'x',
        },
        {
          type: 'bar',
          stack: 'x',
        },
      ],
    }
    this.echarts.setOption(option)
    this.echarts.on('click', function (params) {
      console.log(params)
    })
  },
  destroyed() {
    this.echarts.dispose()
  },
}
</script>

<style>
.bar-echarts {
  width: 300px;
  height: 300px;
  background-color: #0d1426;
}
</style>