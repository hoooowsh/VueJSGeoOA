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
        <tr v-for="(location, index) in searchedLocations" :key="index">
          <td>{{ location.name }}</td>
          <td>{{ location.existance }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  props: {
    searchedLocations: Array,
  },
};
</script>

<style>
/* Add your table styles here if needed */
</style>
