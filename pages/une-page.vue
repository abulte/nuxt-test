<template>
  <div class="container">
    <div>
      <h1 class="title">
        nuxt-app
      </h1>
      <h2 class="subtitle">
        Une page
      </h2>
      <div id="map"></div>
    </div>
  </div>
</template>

<script>
// import Logo from '~/components/Logo.vue'

export default {
  components: {
    // Logo
  },
  mounted () {
    const mapboxgl = require('mapbox-gl')
    const map = new mapboxgl.Map({
      container: 'map', // <div id="map"></div>
      style: 'https://etalab-tiles.fr/styles/osm-bright/style.json',
      center: [8.542, 47.372], // starting position as [lng, lat]
      zoom: 2
    })
    console.log(map)
  },
  head: {
    link: [
      {
        rel: 'stylesheet',
        href: 'https://api.mapbox.com/mapbox-gl-js/v1.10.0/mapbox-gl.css'
      }
    ]
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}

#map {
  width: 200px;
  height: 200px;
}
</style>
