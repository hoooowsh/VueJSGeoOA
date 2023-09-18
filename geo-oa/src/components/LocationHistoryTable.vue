<template>
  <div>
    <table>
      <thead>
        <tr>
          <th>Name</th>
          <th>Existance</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(location, index) in displayedLocations" :key="index">
          <td>
            <input
              type="checkbox"
              v-model="selectedLocations"
              :value="location"
            />
          </td>
          <td>{{ location.name }}</td>
          <td>{{ location.existance }}</td>
        </tr>
      </tbody>
    </table>
    <div>Page: {{ currentPage }}</div>
    <button @click="deleteSelected">Delete Selected</button>
    <button @click="nextPage">Next Page</button>
  </div>
</template>

<script>
export default {
  props: {
    searchedLocations: Array,
  },
  data() {
    return {
      selectedLocations: [], // Array to hold selected locations
      currentPage: 1,
      itemsPerPage: 10,
    };
  },
  computed: {
    // Calculate the locations to display based on current page and items per page
    displayedLocations() {
      const startIndex = (this.currentPage - 1) * this.itemsPerPage;
      const endIndex = startIndex + this.itemsPerPage;
      return this.searchedLocations.slice(startIndex, endIndex);
    },
    totalPages() {
      return Math.ceil(this.searchedLocations.length / this.itemsPerPage);
    },
  },
};
</script>

<style>
/* Add your table styles here if needed */
</style>
