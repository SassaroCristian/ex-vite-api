<script>
import breweryCard from "./components/breweryCard.vue";
import searchBar from "./components/searchBar.vue";
import axios from 'axios';
import { store } from "./store.js";

export default {
  components: {
    breweryCard,
    searchBar
  },
  data() {
    return {
      store,
    }
  },
  mounted() {
    this.getBrewery();
  },
  methods: {
    getBrewery() {
      axios.get(this.store.apiUrl).then(result => {
        this.store.breweries = result.data;
      });
    },
    handleSearch(searchTerm) {
      store.apiUrl = `https://api.openbrewerydb.org/v1/breweries?by_type=${searchTerm}&per_page=10 `;
      this.getBrewery();
    },
  },
};
</script>

<template>
  <div class="text-center">
    <h1 class="text-5xl font-extrabold p-10  bg-gradient-to-tr from-teal-400 to-teal-600">Discover Polish Brews: Filter
      Your Flavorful Journey by Brewery Type!</h1>
    <searchBar class="m-auto py-10" @search="handleSearch" />
    <div class="flex m-auto flex-wrap justify-center">
      <breweryCard v-for="brewery in store.breweries" :info="brewery" />
    </div>
  </div>
</template>

<style scoped></style>
