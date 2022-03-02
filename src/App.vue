<template>
  <div id="app">
    <Header title="GitHub Portfolio"></Header>
    <Container></Container>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Container from "./components/Container.vue";
import Footer from "./components/Footer.vue";

export default {
  components: {
    Header,
    Container,
    Footer,    
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Roboto&display=swap");

* {
  margin: 0;
  padding: 0;
  font-family: "Roboto", sans-serif;
}
</style>
