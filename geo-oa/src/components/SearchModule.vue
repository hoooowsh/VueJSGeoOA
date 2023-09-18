<template>
  <div>
    <input v-model="searchText" @keyup.enter="handleSearch" />
    <button @click="handleSearch">Search</button>
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
      this.$emit("search", this.searchText + "waaahaha");
    },
  },
};
</script>

<style>
/* Add your styles here */
</style>
