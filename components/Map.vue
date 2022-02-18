<template>
  <div id="map-wrap" style="height: 120vh">
    <client-only>
      <l-map :zoom="13" :center="latLng">
        <l-tile-layer
          url="http://{s}.tile.osm.org/{z}/{x}/{y}.png"
        ></l-tile-layer>
        <l-marker :lat-lng="latLng"></l-marker>
      </l-map>
    </client-only>
  </div>
</template>
<script>
export default {
  type: Array,
  props: {
    latLng: {
      default: [24.55083626738222, 78.19883917152573],
    },
  },
};
</script>
