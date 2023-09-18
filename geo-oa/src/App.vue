<template>
  <div>
    <SearchModule @search="handleSearch" />
    <LocationButton />
    <!-- 
    <LocationMap :location="location" />
    <LocationTable :data="searchedLocations" /> -->
  </div>
</template>

<script>
import LocationButton from "@/components/LocationButton.vue";
import SearchModule from "@/components/SearchModule.vue";
// import LocationMap from "@/components/LocationMap.vue";
// import LocationTable from "@/components/LocationTable.vue";

export default {
  components: {
    SearchModule,
    LocationButton,
    // LocationMap,
    // LocationTable,
  },
  data() {
    return {
      location: null,
      searchedLocations: [],
    };
  },
  methods: {
    /**
     * get the result of searching from SearchModule
     */
    handleSearch(searchResult) {
      console.log(searchResult);

      const newLocation = {
        name: searchResult.address,
        existance: searchResult.existance,
      };

      // Append the new location to the array
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
