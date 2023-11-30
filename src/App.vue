<script>
import breweryCard from "./components/breweryCard.vue"

import axios from 'axios';
import { store } from "./store.js"

export default {
  components: {
    breweryCard
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
  }
}
</script>

<template>
  <main>
    <breweryCard v-for="brewery in store.breweries" :info="brewery" />
  </main>
</template>

<style scoped></style>
