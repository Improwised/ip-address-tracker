<template>
  <div class="middle-input-div col-lg-3 col-sm-12">
    <label class="middle-label">{{ title }}</label>
    <h1 class="middle-input">{{ value }}</h1>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    value: {
      type: String,
      required: true,
    },
  },
}
</script>

<style scoped>
.middle-input-div {
  padding: 2% 2% 4%;
}

.middle-label {
  letter-spacing: 1px;
  font-size: 15px;
  font-weight: 700;
}
</style>
