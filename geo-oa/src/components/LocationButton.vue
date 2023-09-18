<template>
  <div class="geo-button">
    <button @click="getLocation">Get Current Location</button>
  </div>
</template>

<script>
export default {
  methods: {
    /**
     * helper function to get latitude and longtitude while geobutton gets clicked
     */
    getLocation() {
      // if geolocation supported in this browser
      if ("geolocation" in navigator) {
        navigator.geolocation.getCurrentPosition((position) => {
          const { latitude, longitude } = position.coords;
          console.log(latitude, longitude);
          return { latitude, longitude };
        });
      }
      // otherwise pop up an alert
      else {
        alert("Geolocation is not supported by this browser.");
      }
    },
  },
};
</script>

<style scoped>
.geo-button {
  text-align: center;
  cursor: pointer;
}
</style>
