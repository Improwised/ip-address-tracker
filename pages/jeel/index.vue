<template>
  <div>
    <Header
      v-model="ipAddress"
      :ip-address="ipAddress"
      :get-ip-data="getIpData"
    />
    <Middledata :ip-data="ipData" />
    <div class="map">
      <Map :lat-lng="lat_lng" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      ipAddress: '',
      ipData: {
        ip: '',
        location: {
          country: '',
          region: '',
          timezone: '',
        },
        isp: '',
      },
      lat_lng: [10.639455173438886, 9.292239482108867],
    }
  },
  methods: {
    async getIpData() {
      const res = await this.$axios.$get(
        'https://geo.ipify.org/api/v2/country,city?apiKey=at_5jNicfri3nLpD3hOwy9LnQVQ89cf7&ipAddress=' +
          this.ipAddress
      )
      this.ipData = res
      this.lat_lng = [res.location.lat, res.location.lng]
    },
  },
}
</script>
<style>
.middle-div {
  display: flex;
  position: relative;
  z-index: 1;
  background: white;
  box-shadow: 0 0 20px 0 rgb(0 0 0 / 50%);
  border-radius: 0.7em;
  bottom: 70px;
  margin: auto 15%;
  padding: 5% auto;
}

.map {
  position: relative;
  bottom: 160px;
  z-index: 0;
}
</style>
