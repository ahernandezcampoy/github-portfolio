<template>
  <div id="container" class="container">
    <h2>Proyectos</h2>
    <img
      src="https://avatars.githubusercontent.com/u/28893583?v=4"
      alt="User avatar"
      class="image"
      width="100"
      loading="lazy"
    />
    <hr />
    <loading v-if="load" />
    <div id="cards" class="cards" v-for="project in projects" :key="project.id">
      <Card
        :name="project.name"
        :description="project.description"
        :author="project.owner.login"
        :url="project.html_url"
        :homepage="project.homepage"
      />
    </div>
  </div>
</template>

<script>
import Card from "./Card.vue";
import Loading from "./Loading.vue";

export default {
  components: {
    Card,
    Loading,
  },

  data() {
    return {
      projects: [],
      load: false,
    };
  },

  mounted() {
    this.getProjects();
  },

  methods: {
    async getProjects() {
      this.load = true;
      const res = await fetch(
        "https://api.github.com/users/ahernandezcampoy/repos"
      );
      const data = await res.json();
      this.projects = data;
      this.load = false;

      console.log(data[0]);
      //https://github.com/ahernandezcampoy/contador-vue-pwa
    },
  },
};
</script>

<style scoped>
.container {
  overflow: hidden;
  border: solid 1px #eee;
  box-shadow: 1px 1px 4px #333;
  text-align: center;
}

.image {
  border-radius: 50%;
}

.cards {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>
