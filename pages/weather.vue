<template lang="html">
  <div class="container">
      <div class="card card-custom mb-3">
          <div class="card-body">
              <form class="" @submit.prevent="searchWeatherInfo">
              <div class="form-group">
                  <label for="city">Enter City Name</label>
                  <input type="text" class="form-control" name="" v-model="city">
              </div>
          </form>
          </div>
      </div>

      <div class="card card-custom">
          <div class="card-header">
              <h1 class="card-title h5 mb-0">Weather Report {{city}} City</h1>
          </div>
          <div class="card-body">

          </div>
      </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      city: "London"
    }
  },
  methods: {
    searchWeatherInfo() {
      this.$axios.$get(`https://api.openweathermap.org/data/2.5/weather?q=London&appid=950fba956f82992f9d0e7a9e3d35bfb4`).then(res => console.log(res))
    }
}
  }
</script>

<style lang="css" scoped>
</style>
