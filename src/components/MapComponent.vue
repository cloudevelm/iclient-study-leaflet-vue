<template>
  <div id="map"></div>
</template>

<script>
export default {
  name: "MapComponent",
  mounted() {
    this.init()
  },
  data() {
    return {
      url: 'http://localhost:8090/iserver/services/map-kh_L2/rest/maps/China_Province3395@kh_L2'
    }
  },
  methods: {
    init() {
      const L = window.L
      window.map = L.map('map', {
        crs: L.CRS.EPSG3395,
        center: [29.94, 104.49],
        maxZoom: 18,
        zoom: 1
      })
      L.supermap.tiledMapLayer(this.url).addTo(window.map)
    }
  }
}
</script>

<style scoped>
#map {
  width: 100%;
  height: 100%;
}
</style>