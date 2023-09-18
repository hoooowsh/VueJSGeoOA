<template>
  <div>
    <input v-model="searchText" @keyup.enter="handleSearch" />
    <button @click="handleSearch">Search Location</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      searchText: "",
    };
  },
  methods: {
    /**
     * Search location helper, use google api here and return the location. Also add the search history to frontend temp list
     */
    handleSearch() {
      // Send the search text to the parent component using an event
      console.log("serjj", this.searchText);
      const newLocation = {
        address: this.searchText,
        existance: false,
      };
      this.$emit("search", newLocation);
    },
  },
};
</script>

<style>
/* Add your styles here */
</style>
