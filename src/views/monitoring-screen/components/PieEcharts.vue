<template>
  <div class="pie-echarts" ref="pieEcharts"></div>
</template>

<script>
export default {
  name: 'PieEcharts',
  data() {
    return {
      echarts: null,
    }
  },
  mounted() {
    this.echarts = echarts.init(this.$refs.pieEcharts)
    const option = {
      dataset: {
        source: [
          ['Search Engine', 1048],
          ['Direct', 735],
          ['Email', 580],
          ['Union Ads', 484],
          ['Video Ads', 300],
        ],
      },
      tooltip: {
        trigger: 'item',
      },
      series: [
        {
          name: 'Access From',
          type: 'pie',
          radius: '50%',
          emphasis: {
            itemStyle: {
              shadowBlur: 10,
              shadowOffsetX: 0,
              shadowColor: 'rgba(0, 0, 0, 0.5)',
            },
          },
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
.pie-echarts {
  width: 300px;
  height: 300px;
  background-color: #0d1426;
}
</style>