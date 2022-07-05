<template>
  <div class="map-container" ref="mapContainer"></div>
</template>

<script>
export default {
  name: 'BaiduMap',
  data() {
    return {
      map: null,
    }
  },
  mounted() {
    this.map = new BMapGL.Map(this.$refs.mapContainer)
    const point = new BMapGL.Point(116.404, 39.915)
    this.map.enableScrollWheelZoom(true)
    this.map.centerAndZoom(point, 15)
    this.map.setMapStyleV2({
      styleId: '02b07042d6a205a839fc7cff62d6d4d1',
    })
  },
  methods: {},
}
</script>

<style scoped>
.map-container {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 0;
  width: 100vw;
  height: 100vh;
}
</style>