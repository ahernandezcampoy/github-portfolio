<template>
  <div id="card" class="card">
    <h4>{{ name }}</h4>
    <p>
      {{ description }}
    </p>
    <p>
      <strong>Author: {{ author }} </strong>
    </p>
    <custom-button :url="url"></custom-button>
    <custom-button
      :url="homepage"
      color="red"
      v-if="homepage != null"
      title="Deploy"
    ></custom-button>
  </div>
</template>

<script>
import CustomButton from "./CustomButton.vue";

export default {
  components: {
    CustomButton,
  },

  props: {
    name: String,
    description: String,
    author: String,
    url: String,
    homepage: String,
  },
};
</script>

<style scoped>
.card {
  border: solid 1px #eee;
  box-shadow: 1px 1px 4px #333;
  text-align: center;
  width: 250px;
  margin: 7px;
}
</style>
