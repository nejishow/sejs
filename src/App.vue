<template>
  <div>
    <Header></Header>
    <div class="container-fluid">
      <router-view />
    </div>

    <Footer></Footer>
  </div>
</template>
<script>
import Header from "./views/Header.vue";
import Footer from "./views/Footer.vue";
export default {
  components: {
    Header,
    Footer
  },
  methods: {
    beforeEnter() {
      this.$root.$emit("scrollBeforeEnter");
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
[class^="col"] {
  margin-top: 5px;
  border-radius: 20px;
}
.container-fluid {
  background: white;
}
.row {
  margin-bottom: 30px;
  justify-content: center;
}
</style>
