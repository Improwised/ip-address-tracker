<template>
  <header class="header-div">
    <h1 class="header-heading">IP Address Tracker</h1>
    <div class="d-inline-flex">
      <input
        v-model="newipaddress"
        class="ip-input px-5"
        placeholder="Search for any ip address"
        size="40"
      />
      <button class="ip-button" @click="getipdata">
        <img :src="require('@/static/icon-arrow.svg')" alt="arrow icon" />
      </button>
    </div>
  </header>
</template>

<script>
export default {
  props: {
    ipaddress: {
      type: Object,
      default: null,
    },
    getipdata: {
      type: Function,
      default: null,
    },
  },
  data() {
    return {
      newipaddress: this.ipaddress,
    }
  },
}
</script>

<style scoped>
.header-div {
  text-align: center;
  background-image: url('@/static/pattern-bg.png');
  background-size: cover;
  padding-top: 2%;
  padding-bottom: 8%;
  position: relative;
  z-index: 0;
}

.header-heading {
  font-weight: 700;
  font-size: 35px;
  color: white;
  font-family: sans-serif;
  padding-left: 3%;
  padding-bottom: 1%;
}

.ip-input {
  border-radius: 15px 0 0 15px;
  border-style: none;
  font-size: 20px;
  padding: 2.5% 5%;
  outline: none;
  cursor: pointer;
}

.ip-button {
  border-style: none;
  border-radius: 0 15px 15px 0;
  background-color: rgb(66 65 65);
  color: white;
  padding-left: 4%;
  padding-right: 4%;
  cursor: pointer;
}
</style>
