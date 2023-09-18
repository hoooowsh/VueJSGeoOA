<template>
  <div>
    <SearchModule @search="handleSearch" />
    <LocationButton />
    <LocationHistoryTable
      :searchedLocations="searchedLocations"
      @delete-locations="handleDeleteSelected"
    />
  </div>
</template>

<script>
import LocationButton from "@/components/LocationButton.vue";
import SearchModule from "@/components/SearchModule.vue";
import LocationHistoryTable from "@/components/LocationHistoryTable.vue";

export default {
  components: {
    SearchModule,
    LocationButton,
    LocationHistoryTable,
  },
  data() {
    return {
      location: null,
      searchedLocations: [],
    };
  },
  methods: {
    handleSearch(searchResult) {
      const newLocation = {
        name: searchResult.address,
        existance: searchResult.existance,
      };

      // Append the new location to the array for displaying the list
      this.searchedLocations.push(newLocation);
    },
    handleDeleteSelected(selectedLocations) {
      selectedLocations.forEach((location) => {
        const index = this.searchedLocations.indexOf(location);
        if (index > -1) {
          this.searchedLocations.splice(index, 1);
        }
      });
    },
  },
};
</script>

<style>
/* Add your global styles here */
</style>
