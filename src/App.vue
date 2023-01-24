<script >

import AppHeader from "./components/AppHeader.vue";
import AppCard from "./components/AppCard.vue";
import axios from "axios";
import { store } from "./data/store.js";
export default {
  data() {
    return {
      store
    }
  },
  created() {
    axios.get("https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?per=10&page=1").then((res) => { store.AllPokemons = res.data.docs })
  },
  components: {
    AppHeader, AppCard
  },
}


</script>

<template>
  <section>
    <app-header></app-header>
    <app-card></app-card>

  </section>

</template>

<style lang="scss" scoped>
@use "./assets/style.scss"
</style>
