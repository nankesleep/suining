<template>
  <div class="main">
    <div id="map"></div>
  </div>
</template>
 
<script>
// 天地图key:f0441b584b9afa8e10bbc43aa2aabfbe
import { onMounted } from '@vue/runtime-core';
export default {
  setup() {
    onMounted(() => {
      const url1 = "http://t0.tianditu.com/DataServer?T=vec_w&x={x}&y={y}&l={z}&tk=f0441b584b9afa8e10bbc43aa2aabfbe";
      const url2 = "http://t0.tianditu.com/DataServer?T=cva_w&x={x}&y={y}&l={z}&tk=f0441b584b9afa8e10bbc43aa2aabfbe";
      // 初始化地图信息
      let map = new ol.Map({
        controls: ol.control.defaults({ attribution: false, zoom: false, rotate: false }),
        target: 'map',
        layers: [],
        view: new ol.View({
          projection: "EPSG:4326",
          center: [106.532322, 29.573684],
          zoom: 12,
          //最小级别
          minZoom: 4
          //最大级别
        })
      });
      //添加图层
      let layer1 = new ol.layer.Tile({
        source: new ol.source.XYZ({
          url: url1,
          wrapX: false
        }),
      });
      let layer2 = new ol.layer.Tile({
        source: new ol.source.XYZ({
          url: url2,
        }),
      });
      map.addLayer(layer1);
      map.addLayer(layer2);
    })
  }
}
</script>
 
<style lang="scss" scoped>
.main {
  position: absolute;
  width: 100%;
  height: calc(100vh - 60px);
}

#map {
  width: 100%;
  height: calc(100vh - 60px);
}
</style>