<template>
  <div>
    <SearchModule @search="handleSearch" />
    <LocationButton />
    <LocationHistory :searchedLocations="searchedLocations" />
  </div>
</template>

<script>
import LocationButton from "@/components/LocationButton.vue";
import SearchModule from "@/components/SearchModule.vue";
import LocationHistory from "@/components/LocationHistoryTable.vue";
// import LocationTable from "@/components/LocationTable.vue";

export default {
  components: {
    SearchModule,
    LocationButton,
    LocationHistory,
    // LocationTable,
  },
  data() {
    return {
      location: null,
      searchedLocations: [{ name: "test", existance: "test" }],
    };
  },
  methods: {
    /**
     * get the result of searching from SearchModule
     */
    handleSearch(searchResult) {
      const newLocation = {
        name: searchResult.address,
        existance: searchResult.existance,
      };
      console.log(newLocation);
      // Append the new location to the array for displaying the list
      this.searchedLocations.push(newLocation);

      console.log(this.searchedLocations);
    },

    handleDeleteSelected() {
      // Delete selected rows and their markers
    },
  },
};
</script>

<style>
/* Add your global styles here */
</style>
