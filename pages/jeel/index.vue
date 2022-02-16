<template>
  <div>
    <Header :ipaddress="ipaddress" :ipdata="ipadata" :getipdata="getipdata" />
    <div class="middle-div row">
      <Middledata :title="'IP ADDRESS'" :value="ipdata.ip" />
      <Middledata
        :title="'LOCATION'"
        :value="ipdata.location.country + ' ' + ipdata.location.region"
      />
      <Middledata :title="'TIMEZONE'" :value="ipdata.location.timezone" />
      <Middledata :title="'ISP'" :value="ipdata.isp" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      ipaddress: '',
      ipdata: {
        ip: '',
        location: {
          country: '',
          region: '',
          timezone: '',
        },
        isp: '',
      },
    }
  },
  methods: {
    async getipdata() {
      const res = await this.$axios.$get(
        'https://geo.ipify.org/api/v2/country?apiKey=at_5jNicfri3nLpD3hOwy9LnQVQ89cf7&ipAddress=' +
          this.ipaddress
      )
      this.ipdata = res
    },
  },
}
</script>
<style scoped>
.middle-div {
  display: flex;
  position: relative;
  z-index: 1;
  background: white;
  box-shadow: 0 0 20px 0 rgb(0 0 0 / 50%);
  border-radius: 0.7em;
  bottom: 60px;
  margin: auto 15%;
  padding: 5% auto;
}
</style>
