<script>
import ProjectCard from '../components/ProjectCard.vue';
import axios from 'axios';

export default {
  name: 'ProjectList',
  data() {
    return {
      projects: [],
      baseUrl: 'http://127.0.0.1:8000',
      apiUrl: {
        projects: '/api/projects',
      },
    };
  },
  components: {
    ProjectCard,
  },
  methods: {
    getProjects() {
      axios
        .get(this.baseUrl + this.apiUrl.projects)
        .then((response) => {
          console.log(response);
          this.projects = response.data.data.data;
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
  created() {
    this.getProjects();
  },
};
</script>

<template>
  <main class="bg-info">
    <div class="container py-3">
      <h1 class="text-center">Elenco dei Progetti</h1>
      <div class="row mt-4">
        <div class="col col-md-4 g-4" v-for="project in projects">
          <ProjectCard :project="project" />
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped lang="scss">
h1 {
  color: green;
  text-transform: uppercase;
}
.card {
  border: 2px solid black;
  background-color: lightgray;
}
</style>
