<script>
import axios from "axios";
import { store } from "./data/store";
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "App",
  components: {
    Header,
    Main,
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
        console.log(results.data);
        this.store.projects = results.data.data;
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
  <Main />
  <Footer />
</template>

<style lang="scss">
@use './scss/main.scss';
</style>
