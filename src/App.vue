<script>
import axios from "axios";
import { store } from "./data/store";
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "App",
  components: {
    Header,
    Footer,
  },
  data() {
    return {
      store,
    };
  },
  methods: {
    getApi() {
      axios.get(store.apiUrl + "projects").then((results) => {
        console.log(store.projects);
        this.store.projects = results.data.data;
        this.store.links = results.data.links;
        console.log(store.links);
      });
    },
  },
  mounted() {
    this.getApi();
  },
};
</script>

<template>
  <Header />
  <div class="container">
    <RouterView/>
  </div>
  <Footer />
</template>

<style lang="scss">
@use './scss/main.scss';
</style>
