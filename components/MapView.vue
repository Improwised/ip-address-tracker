<template>
  <div class="map">
    <no-ssr>
      <div
        id="map-wrap"
        style="height: 55vh; width: 114vh; margin-top: 200px"
        class="z-0"
      >
        <l-map :zoom="1" :center="lat_lng">
          <l-tile-layer
            url="http://{s}.tile.osm.org/{z}/{x}/{y}.png"
          ></l-tile-layer>
          <l-marker :lat-lng="lat_lng">
            <img :src="require('~/static/icon-location.svg')" />
          </l-marker>
        </l-map>
      </div>
    </no-ssr>
  </div>
</template>

<script>
export default {
  props: ["lat_lng"],

  head() {
    return {
      link: [
        {
          rel: "stylesheet",
          href: "https://unpkg.com/leaflet@1.6.0/dist/leaflet.css",
        },
      ],
    };
  },
};
</script>
