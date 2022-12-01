<script setup>
  const { geolonia } = window;
  const mapDom = document.getElementById('map')
  if (mapDom) {
    const map = new geolonia.Map('#map')
    map.on('load', () => {
      console.log("map loaded")
    })
  }
</script>

<template>
  <div id="map"></div>
</template>
