<script lang="ts">
import mapboxgl from "mapbox-gl";

export default {
  name: "TravelMap",
  data() {
    return {
      apiKey: import.meta.env.VITE_MAPBOX_KEY,
    };
  },
  mounted() {
    this.createMap();
  },
  methods: {
    createMap() {
      mapboxgl.accessToken = this.apiKey;
      this.map = new mapboxgl.Map({
        container: "map",
        style: "mapbox://styles/mapbox/streets-v9",
        minzoom: 1.3,
        center: [13.4, 52.52], // Berlin
        zoom: 3,
      });
    },
  },
};
</script>

<template>
  <h1>Travel Map</h1>
  <div id="map"></div>
</template>

<style scoped>
h1 {
  margin: 2vh;
}
#map {
  width: 100%;
  min-height: 70vh;
  position: relative;
}
</style>
