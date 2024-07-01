<template>
  <div id="map"></div>
</template>

<style lang="scss">
@import url('../../node_modules/ol/ol.css');
#map {
  height: 100vh;
  width: 100%;
  margin: 0;
  padding: 0;
  background-color: black;
}
</style>

<script setup lang="ts">
import Map from 'ol/Map';
import OSM from 'ol/source/OSM';
import TileLayer from 'ol/layer/Tile';
import View from 'ol/View';
import { onMounted } from 'vue';

onMounted(() => {
  new Map({
    target: 'map',
    layers: [
      new TileLayer({
        source: new OSM(),
      }),
    ],
    view: new View({
      center: [0, 0],
      zoom: 2,
    }),
  });
});
</script>
