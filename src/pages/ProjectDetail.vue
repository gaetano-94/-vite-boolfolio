<script>
import axios from 'axios';
import store from '../store';

export default {
  name: 'ProjectDetail',
  data() {
    return {
      store,
      project: {},
    };
  },
  methods: {
    getProject() {
      axios
        .get(
          this.store.api.baseUrl +
            this.store.api.apiUrl.projects +
            '/' +
            this.$route.params.slug
        )
        .then((response) => {
          this.project = response.data.result;
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
  created() {
    this.getProject();
  },
};
</script>

<template>
  <div class="container-max">
    <div class="py-4 container">
      <h1>{{ project.title }}</h1>
      <p>{{ project.content }}</p>
      <h6>
        <router-link :to="{ name: 'projects' }" class="text-decoration-none"
          >Torna ai Progetti</router-link
        >
      </h6>
    </div>
  </div>
</template>

<style scoped lang="scss">
.container-max {
  height: 100vh;
}
</style>
